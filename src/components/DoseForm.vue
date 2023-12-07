<script setup lang="ts">
import { ref } from 'vue';

const medicineName = ref();
const doseFrequency = ref();
const days = ref();
const doneDoses = ref();

const handleSubmit = () => {
  console.log(medicineName.value, doseFrequency.value, days.value);
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <p>
      I need to take
      <label for="med-name">
        <!-- Put this smaller right above the input -->
        <!-- Or this follows the Material style where it looks like placeholder text and then floats up -->
        <span class="tiny"> Medicine Name </span>
        <!-- Current design thought: br 3 or 4, dark orange bg, goes lighter (white?) when focused -->
        <input id="med-name" type="text" v-model="medicineName" />
      </label>
      every
      <label for="frequency">
        Dose Frequency (hours)
        <input id="frequency" type="text" v-model="doseFrequency" />
      </label>
      hours for
      <label for="days">
        Days
        <input id="days" type="text" v-model="days" />
      </label>
      days and I took
      <label for="done-doses">
        Done Doses
        <input id="done-doses" type="text" v-model="doneDoses" />
      </label>
      already.
    </p>

    <button type="submit">Calculate!</button>
  </form>
</template>

<style module></style>
