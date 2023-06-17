<template>
    <div class="calendar-container">
      <div class="calendar">
        <div class="calendar-header">
          <div class="month-selector">
            <button @click="prevMonth('checkin')"><i class="fa-solid fa-angle-left"></i></button>
            <div>
              <span class="month me-1">{{ currentMonthName(checkinMonth) }}</span>
              <span class="year">{{ currentYear }}</span>
            </div>
            <button @click="nextMonth('checkin')"><i class="fa-solid fa-angle-right"></i></button>
          </div>
          <div class="days-of-week">
            <span v-for="day in daysOfWeek" :key="day">{{ day }}</span>
          </div>
        </div>
        <div class="calendar-body">
          <span
            v-for="date in calendarDates.checkin"
            :key="date"
            :class="[{ 'selected-date': isSelectedDate(date, 'checkin') }, { 'disabled-date': isDisabledDate(date, 'checkin') }]"
            @click="selectDate(date, 'checkin')"
          >
            {{ date }}
          </span>
        </div>
      </div>
  
      <div class="calendar">
        <div class="calendar-header">
          <div class="month-selector">
            <button @click="prevMonth('checkout')"><i class="fa-solid fa-angle-left"></i></button>
            <div>
              <span class="month me-1">{{ currentMonthName(checkoutMonth) }}</span>
              <span class="year">{{ currentYear }}</span>
            </div>
            <button @click="nextMonth('checkout')"><i class="fa-solid fa-angle-right"></i></button>
          </div>
          <div class="days-of-week">
            <span v-for="day in daysOfWeek" :key="day">{{ day }}</span>
          </div>
        </div>
        <div class="calendar-body">
          <span
            v-for="date in calendarDates.checkout"
            :key="date"
            :class="[{ 'selected-date': isSelectedDate(date, 'checkout') }, { 'disabled-date': isDisabledDate(date, 'checkout') }]"
            @click="selectDate(date, 'checkout')"
          >
            {{ date }}
          </span>
        </div>
      </div>
    </div>
  
    <!-- <div class="selected-dates">
      Check-in Date: {{ checkinDate }}<br>
      Check-out Date: {{ checkoutDate }}
    </div> -->
  
    <button class="keyboard-button"><i class="fa-solid fa-keyboard"></i></button>
    <button class="reset-button" @click="resetDates">Clear dates</button>
</template>
  
  <script>
export default {
  data() {
    return {
      checkinDate: '',
      checkoutDate: '',
      checkinMonth: new Date().getMonth(),
      checkoutMonth: new Date().getMonth() + 1,
      currentYear: new Date().getFullYear(),
      daysOfWeek: ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa'],
      calendarDates: {
        checkin: [],
        checkout: []
      }
    };
  },
  mounted() {
    this.generateCalendar('checkin');
    this.generateCalendar('checkout');
  },
  methods: {
    prevMonth(type) {
      if (type === 'checkin') {
        this.checkinMonth--;
        if (this.checkinMonth < 0) {
          this.checkinMonth = 11;
          this.currentYear--;
        }
        this.generateCalendar('checkin');
      } else if (type === 'checkout') {
        this.checkoutMonth--;
        if (this.checkoutMonth < 0) {
          this.checkoutMonth = 11;
          this.currentYear--;
        }
        this.generateCalendar('checkout');
      }
    },
    nextMonth(type) {
      if (type === 'checkin') {
        this.checkinMonth++;
        if (this.checkinMonth > 11) {
          this.checkinMonth = 0;
          this.currentYear++;
        }
        this.generateCalendar('checkin');
      } else if (type === 'checkout') {
        this.checkoutMonth++;
        if (this.checkoutMonth > 11) {
          this.checkoutMonth = 0;
          this.currentYear++;
        }
        this.generateCalendar('checkout');
      }
    },
    currentMonthName(month) {
      const monthNames = [
        'January', 'February', 'March', 'April', 'May', 'June', 'July',
        'August', 'September', 'October', 'November', 'December'
      ];
      return monthNames[month];
    },
    isSelectedDate(date, type) {
      if (type === 'checkin') {
        return date === this.checkinDate;
      } else if (type === 'checkout') {
        return date === this.checkoutDate;
      }
    },
    isDisabledDate(date, type) {
      const currentDate = new Date();
      const currentYear = currentDate.getFullYear();
      const currentMonth = currentDate.getMonth();
      const currentDay = currentDate.getDate();

      if (type === 'checkin') {
        if (
          this.currentYear < currentYear ||
          (this.currentYear === currentYear && this.checkinMonth < currentMonth) ||
          (this.currentYear === currentYear && this.checkinMonth === currentMonth && date < currentDay)
        ) {
          return true;
        }
      } else if (type === 'checkout') {
        if (
          this.currentYear < currentYear ||
          (this.currentYear === currentYear && this.checkoutMonth < currentMonth) ||
          (this.currentYear === currentYear && this.checkoutMonth === currentMonth && date < currentDay)
        ) {
          return true;
        }
      }

      return false;
    },
    selectDate(date, type) {
      if (type === 'checkin') {
        this.checkinDate = this.formatDate(date, this.checkinMonth, this.currentYear);
      } else if (type === 'checkout') {
        this.checkoutDate = this.formatDate(date, this.checkoutMonth, this.currentYear);
      }
    },
    formatDate(day, month, year) {
      const formattedMonth = (month + 1).toString().padStart(2, '0');
      const formattedDay = day.toString().padStart(2, '0');
      return `${year}-${formattedMonth}-${formattedDay}`;
    },
    generateCalendar(type) {
      const month = (type === 'checkin') ? this.checkinMonth : this.checkoutMonth;
      const firstDay = new Date(this.currentYear, month, 1).getDay();
      const lastDay = new Date(this.currentYear, month + 1, 0).getDate();

      this.calendarDates[type] = [];

      for (let i = 0; i < firstDay; i++) {
        this.calendarDates[type].push('');
      }
      for (let date = 1; date <= lastDay; date++) {
        this.calendarDates[type].push(date);
      }
    },
    resetDates() {
      this.checkinDate = '';
      this.checkoutDate = '';
    }
  }
};
</script>
  
<style>
  
</style>



   