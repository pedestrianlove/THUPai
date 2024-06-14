<script setup>
import { computed } from 'vue';
import semester from '~/semesterConfig.json';

const semesterTag = computed(() => `${semester.YEAR} 學年度 第 ${semester.SEMESTER} 學期`);
const semesterTagUrl = computed(() => `https://course.thu.edu.tw/view-dept/${semester.YEAR}/${semester.SEMESTER}`);
</script>
<template>
  <a id="semester-tag" class="navbar-item" :href="semesterTagUrl" target="_blank" rel="noopener noreferrer">
    {{ semesterTag }}
  </a>
</template>
