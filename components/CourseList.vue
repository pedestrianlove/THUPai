<script setup>
const props = defineProps({
  courses: {
    type: Array,
  },
  depData: {
    type: Object,
  },
});
</script>
<template>
  <div class="result course-panel course-list">
    <template v-for="course in courses" :key="course.id">
      <CourseItem :course="course" :depData="depData" />
    </template>
  </div>
</template>
