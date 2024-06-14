<template>
  <div class="container is-widescreen">
    <div class="columns is-desktop">
      <div class="column is-one-quarter-desktop sidebar">
        <DepartmentDropdown />
        <CourseSearch />
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
