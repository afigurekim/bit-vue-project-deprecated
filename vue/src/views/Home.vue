<template>
  <v-container
    fill-height
    fluid
    grid-list-xl
  >
    <v-layout wrap>
      <v-flex
        md24
        lg12
      >
        <material-card
          color="info"
          title="날짜 선택"
          text="다이어리를 열람/기록할 날짜를 선택해주세요"
        >
          <FullCalendar defaultView="dayGridMonth" :plugins="calendarPlugins" locale="ko" />
        </material-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>

import FullCalendar from '@fullcalendar/vue'
import dayGridPlugin from '@fullcalendar/daygrid'

export default {
  components: {
    FullCalendar
  },
  data () {
    return {
      calendarPlugins: [ dayGridPlugin ]
    }
  },
  methods: {
    complete (index) {
      this.list[index] = !this.list[index]
    }
  }
}
</script>

<style lang="scss">

@import '../../node_modules/@fullcalendar/core/main.css';
@import '../../node_modules/@fullcalendar/daygrid/main.css';

</style>
