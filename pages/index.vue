<script setup lang="ts">
import semester from "~/semesterConfig.json";

let query = reactive({
  department: 0,
  search: "",
});

const APP_URL = "https://pedestrianlove.github.io/THUPai";

const { data: courseData, pending: courseDataPending, error: courseDataError }
  = await useFetch(APP_URL + `/course-data/${semester.YEAR}${semester.SEMESTER}-data.json`);
const { data: depData, pending: depDataPending, error: depDataError }
  = await useFetch(APP_URL + `/course-data/${semester.YEAR}${semester.SEMESTER}-dep-data.json`);
</script>
<template>
  <div class="container is-widescreen">
    <div class="columns is-desktop">
      <div class="column is-one-quarter-desktop sidebar">
        <DepartmentDropdown v-model="query.department" :departments="depData" />
        <CourseSearch v-model="query.search" :disabled="courseDataPending || (courseDataError != null)" />
        <CourseList />
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
