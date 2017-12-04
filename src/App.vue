<template>
  <div id="main-app">
    <appointments-list
      :appointments = 'theAppointments'
    />
  </div>
    
</template>

<script>

import moment from 'moment'
import AppointmentList from './AppointmentList.vue'

export default {
  name: 'MainApp',
  data () {
    return {
      theAppointments: []
    }
  },

  components: {
    'appointments-list': AppointmentList
  },

  created: function() {
    $.getJSON('./dist/appointments.json')
      .done( info => {
        this.theAppointments = info
      });
  }
}
</script>

<style lang="scss" scoped>

</style>
