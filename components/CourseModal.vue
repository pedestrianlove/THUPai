<template>
  <div class="modal">
    <div class="modal-background"></div>
    <div class="modal-content">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title"></p>
          <a href="#" class="card-header-icon">
            <span class="icon">
              <i class="fas fa-times" aria-hidden="true"></i>
            </span>
          </a>
        </header>
        <div class="card-content">
          <div class="content">
            <dl class="dl-horizontal">
              <dt>課號</dt>
              <dd></dd>
              <dt>開課系所</dt>
              <dd></dd>
              <dt>學分</dt>
              <dd></dd>
              <dt>教師</dt>
              <dd></dd>
              <dt>上課時間 / 教室</dt>
              <dd></dd>
              <dt>備註</dt>
              <dd></dd>
              <dt>課程概述</dt>
              <dd></dd>
              <dt>評分方式</dt>
              <dd>
                <table class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">
                  <thead>
                    <th>項目</th>
                    <th>配分</th>
                    <th>說明</th>
                  </thead>

                  <tbody>
                  </tbody>
                </table>
              </dd>
            </dl>
          </div>
        </div>
        <footer class="card-footer">
          <a href="#" target="_blank" id="outline" class="card-footer-item">課程綱要</a>
        </footer>
      </div>
    </div>
  </div>
</template>
