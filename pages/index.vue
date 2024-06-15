<script setup>
import semester from "~/semesterConfig.json";

let query = reactive({
  department: "0",
  search: "",
});

const APP_URL = "https://pedestrianlove.github.io/THUPai";

const { data: courseData, error: courseDataError }
  = await useFetch(APP_URL + `/course-data/${semester.YEAR}${semester.SEMESTER}-data.json`);
const { data: depData, error: depDataError }
  = await useFetch(APP_URL + `/course-data/${semester.YEAR}${semester.SEMESTER}-dep-data.json`);

const filteredCourses = computed(() => {
  if (query.department === "0") {
    return [];
  }

  return Object.values(courseData.value)
    .filter((course) => (
      (query.department === "0") ? true : course.department_id === query.department
    ))
    .filter((course) => (
      course.id.includes(query.search) ||
      course.teacher.includes(query.search) ||
      course.name.includes(query.search) ||
      course.brief.includes(query.search)
    ))
    .slice(0, 50);
});
</script>
<template>
  <div class="container is-widescreen">
    <div class="columns is-desktop">
      <div class="column is-one-quarter-desktop sidebar">
        <DepartmentDropdown v-model="query.department" :departments="depData" />
        <CourseSearch v-model="query.search" :disabled="courseDataError || depDataError" />
        <CourseList :courses="filteredCourses" />
        <CourseSelect />
      </div>
      <div class="column">
        <div style="text-align: right; margin: 0.5em;">
          <DownloadTableButton />

          <CopyLinkButton />

          <ClearTableButton />

          <ImportTableButton />
        </div>
        <CourseTimetable />
      </div>
    </div>
  </div>
</template>
