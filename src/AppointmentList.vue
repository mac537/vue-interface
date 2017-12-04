<template>
  <ul class="appointment-list">
    <appointment-item 
      v-for="(item, i) in appointments"
      :appointment="item"
      :key="i"
    />
  </ul>
</template>

<script>

  import AppointmentListItem from './AppointmentListItem.vue'

  export default {
    name: 'AppointmentsList',
    props: ['appointments'],
    components: {
      'appointment-item': AppointmentListItem
    }
  }
</script>

<style lang="scss" scoped>
  .appointment-list{
    margin: 0;
    padding: 0;
    list-style-type: none;
    margin: 10px 5%;
    font-size: 1rem;
  }
</style>