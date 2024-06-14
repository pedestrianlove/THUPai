<script setup>
const department = defineModel();
const props = defineProps({
  departments: Object,
});
</script>
<template>
  <div class="field">
    <p class="control has-icons-left has-icons-right">
      <label for="department-dropdown"></label>
      <select v-model="department" id="department-dropdown" class="input">
        <option value="0" selected>全部系所</option>
        <option v-for="(dep, index) in props.departments" :key="index" :value="index">
          {{ dep }}
        </option>
      </select>
      <span class="icon is-small is-left">
        <i class="fas fa-caret-down"></i>
      </span>
    </p>
  </div>
</template>
