<script>
import ReservationCalendar from './ReservationCalender.vue'

export default {
  name: 'app',
  components: {
    ReservationCalendar
  },
  props: {
    price: Number,
    rating: Number,
    votesNumber: Number,
    unavailableDates: Array,
    chosenDates: Array
  },
  data () {
    return {
      isModalVisible: false
    }
  },
  methods: {
    showModal () {
      this.isModalVisible = true
      this.$refs.componentOne.handleFocus()
    },
    closeModal () {
      this.isModalVisible = false
    }
  }
}
</script>

<template>
  <div class="reservation-form">
    <div class="row">
      <div class="form-field price">298 zł</div>
      <div class="form-field rating">****** 123</div>
      <div class="form-field dates">
        <input class="date-input" placeholder="first date" @click="showModal">
        →
        <input class="date-input" placeholder="second date" @click="showModal">
      </div>
    </div>
    <ReservationCalendar
      autofocus
      ref='componentOne'
      v-show="isModalVisible"
      @close="closeModal"
    />
  </div>
</template>

<style>

body {
  margin-top: 100px;
  font-family: Arial;
}
.reservation-form {
  height: 100%;
  padding-bottom: 20px;
  margin: 0;
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  align-items: center;
  justify-content: center;
}
.row {
  width: auto;
  border: 1px solid grey;
  padding-bottom: 20px;
}
.form-field {
  padding: 5px;
  width: 300px;
  margin: 10px;
  line-height: 20px;
  font-weight: bold;
  font-size: 2em;
  text-align: center;
}
.price {
  text-align: left;
}
.rating {
  text-align: left;
  font-size: 1em;
  border-bottom: 1px solid grey;
}
.dates {
  display: inline-block;
  border: 1px solid grey;
}
.date-input {
  width: 120px;
  border: none;
  font-size: 0.6em;
}

</style>
