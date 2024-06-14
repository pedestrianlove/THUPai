<script setup>
const search = defineModel();
const props = defineProps({
  disabled: Boolean,
});

const placeholder = computed(() => {
  return props.disabled
    ? "載入課程資料中"
    : "課號 / 課名 / 老師 / 備註";
});

</script>
<template>
  <div class="field">
    <p class="control has-icons-left has-icons-right">
      <input v-model="search" id="search-bar" class="input" type="text" :placeholder="placeholder"
        :disabled="props.disabled">
      <span class="icon is-small is-left">
        <i class="fas fa-search"></i>
      </span>
    </p>
  </div>
</template>
