<script setup>
const TIME_MAPPING = {
  'A': "7:10 ~ 8:00",
  1: "8:10 ~ 9:00",
  2: "9:10 ~ 10:00",
  3: "10:20 ~ 11:10",
  4: "11:20 ~ 12:10",
  'B': "12:10 ~ 13:00",
  5: "13:10 ~ 14:00",
  6: "14:10 ~ 15:00",
  7: "15:20 ~ 16:10",
  8: "16:20 ~ 17:10",
  9: "17:20 ~ 18:10",
  10: "18:20 ~ 19:10",
  11: "19:20 ~ 20:10",
  12: "20:20 ~ 21:10",
  13: "21:20 ~ 22:10",
}

function compareTimeIdx(a, b) {
  if (Number.isFinite(a) && Number.isFinite(b)) {
    return parseFloat(a) - parseFloat(b);
  } else {
    let a_val = a, b_val = b;
    if (a === 'A') {
      a_val = 0;
    }
    if (b === 'A') {
      b_val = 0;
    }
    if (a === 'B') {
      a_val = 4.5;
    }
    if (b === 'B') {
      b_val = 4.5;
    }

    return parseFloat(a_val) - parseFloat(b_val);
  }
}

const TIME_IDX = Object.keys(TIME_MAPPING).sort(compareTimeIdx);
</script>
<template>
  <div id="main-table" class="timetable">
    <div class="week-names">
      <div>Mon</div>
      <div>Tue</div>
      <div>Wed</div>
      <div>Thu</div>
      <div>Fri</div>
      <div>Sat</div>
      <div>Sun</div>
    </div>
    <div class="time-interval">
      <div v-for="time in TIME_IDX" :key="time">
        {{ `${time} / ${TIME_MAPPING[time]}` }}
      </div>
    </div>
    <div class="content">
      <template v-for="time in TIME_IDX" :key="time">
        <div v-for="day in [1, 2, 3, 4, 5, 6, 7]" :key="day" :id="`${day}${time}`">
          <!-- <div class="period modal-launcher"> -->
          <!--   <span>Hello</span> -->
          <!-- </div>` -->
        </div>
      </template>
    </div>
  </div>
</template>
