<script setup>
const props = defineProps({
  courses: {
    type: Array,
  },
});
</script>
<template>
  <div class="result course-panel course-list">
    <template v-for="course in courses" :key="course.id">
      <CourseItem :course="course" />
    </template>
  </div>
</template>
