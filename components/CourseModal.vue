<script setup>
const props = defineProps({
  course: Object,
  depData: Object,
});

let modalOn = ref(false);
</script>
<template>
  <b @click="modalOn = true" class="modal-launcher" id="name">
    {{ course.name }}
  </b>
  <div class="modal is-active" v-if="modalOn">
    <div class="modal-background" @click="modalOn = false" />
    <div class="modal-content">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            {{ course.type + "-" + course.name }}
          </p>
          <div href="#" class="card-header-icon" @click="modalOn = false">
            <span class="icon">
              <i class="fas fa-times" aria-hidden="true"></i>
            </span>
          </div>
        </header>
        <div class="card-content">
          <div class="content">
            <dl class="dl-horizontal">
              <dt>課號</dt>
              <dd>{{ course.id }}</dd>
              <dt>開課系所</dt>
              <dd>{{ depData[course.department_id] }}</dd>
              <dt>學分</dt>
              <dd>{{ course.credit }}</dd>
              <dt>教師</dt>
              <dd>{{ course.teacher }}</dd>
              <dt>上課時間 / 教室</dt>
              <dd>{{ course.time }}</dd>
              <dt>備註</dt>
              <dd>{{ course.brief }}</dd>
              <dt>課程概述</dt>
              <dd>{{ course.description }}</dd>
              <dt>評分方式</dt>
              <dd>
                <table class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">
                  <thead>
                    <th>項目</th>
                    <th>配分</th>
                    <th>說明</th>
                  </thead>
                  <tbody>
                    <tr v-for="(item, index) in course.grading" :key="index">
                      <td>{{ item.target }}</td>
                      <td>{{ item.ratio }}</td>
                      <td>{{ item.description }}</td>
                    </tr>
                  </tbody>
                </table>
              </dd>
            </dl>
          </div>
        </div>
        <footer class="card-footer">
          <a :href="course.url" target="_blank" id="outline" class="card-footer-item">課程綱要</a>
        </footer>
      </div>
    </div>
  </div>
</template>
