<script setup>
import { storeToRefs } from "pinia";
import { useCovidStore } from "../stores/counter";
const covidDatadATA = useCovidStore();
const { select } = storeToRefs(covidDatadATA);
const props = defineProps({
  items: String,
});
</script>
<template>
  <div class="col-12 col-md-4 col-lg-4 text-center py-2">
    <div class="d-flex justify-content-between align-items-center">
      <label for="form-select">Select Country Name:</label>
      <select
        class="form-select py-3 rounded-pill shadow-sm border-0 w-50"
        v-model="select"
        aria-label="Country Name"
      >
        <option
          v-for="(item, index) in props.items"
          :key="index"
          :value="item.name"
        >
          {{ item.name }}
        </option>
      </select>
    </div>
  </div>
</template>
