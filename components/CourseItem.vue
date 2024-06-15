<script setup>
const props = defineProps({
  course: Object,
  depData: Object,
});

const courseTypeClass = computed(() => {
  switch (props.course.type) {
    case "必修":
      return "tag is-rounded is-danger";
    case "必選":
      return "tag is-rounded is-info";
    default:
      return "tag is-rounded";
  }
});

// FIXME: implement state management to update the selectedCourse state
</script>
<template>
  <div class="course">
    <p>
      <span id="id-tag" class="tag is-primary is-rounded">
        {{ course.id }}
      </span>
      <CourseModal :course="course" :depData="depData" />
      <span id="type-tag" :class="courseTypeClass">
        {{ course.type }}
      </span>
    </p>
    <p id="detail">
      {{ `${course.teacher}・${+course.credit} 學分` }}
    </p>
    <a class="toggle-course">
      <span class="icon">
        <i class="toggle-icon fas fa-plus"></i>
      </span>
    </a>
  </div>
</template>
