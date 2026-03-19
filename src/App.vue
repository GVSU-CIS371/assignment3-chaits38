<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />

    <ul>
      <!-- Temperature -->
      <li>
        <strong>Temperature:</strong>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>

      <!-- Base Beverage -->
      <li>
        <strong>Base Beverage:</strong>
        <template v-for="base in bases" :key="base.id">
          <label>
            <input
              type="radio"
              name="base"
              :id="`rb${base.id}`"
              :value="base"
              v-model="currentBase"
            />
            {{ base.name }}
          </label>
        </template>
      </li>

      <!-- Creamer -->
      <li>
        <strong>Creamer:</strong>
        <template v-for="creamer in creamers" :key="creamer.id">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`rc${creamer.id}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer.name }}
          </label>
        </template>
      </li>

      <!-- Syrup -->
      <li>
        <strong>Syrup:</strong>
        <template v-for="syrup in syrups" :key="syrup.id">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`rs${syrup.id}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import {
  temps, bases, creamers, syrups,
  currentTemp, currentBase, currentCreamer, currentSyrup,
} from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin-bottom: 10px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  align-items: center;
  color: white;
}
label {
  color: white;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 4px;
  margin-right: 8px;
}
strong {
  min-width: 120px;
  display: inline-block;
}
</style>
