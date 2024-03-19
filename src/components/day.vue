<template>
    <div class="container">
      <h2 class="mt-4 mb-3">Calendrier de  {{ Cday }}</h2>
      <div class="row">
        <div class="col-md-2">Sciences</div>
        <div class="col-md-10">Status</div>
      </div>
      <div class="row" v-for="(hour, index) in hours" :key="index">
        <div class="col-md-2">{{ hour }}</div>
        <div class="col-md-10">
          <div class="form-group">
            <select class="form-control" v-model="selectedStatus[index]"
          v-bind:class="{
            'text-success': selectedStatus[index] === 'available',
            'text-danger': selectedStatus[index] === 'busy'
          }">
              <option value="available">Valable</option>
              <option value="busy">Non-valable </option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props:{
    Cday:''
    },
    data() {
      return {
        // Change the day name as needed
        hours: [],
        selectedStatus: [] // Store the status for each hour
      };
    },
    created() {
      // Generate a list of hours from 00:00 to 23:00
      for (let i = 9; i < 19; i++) { 
        const hour = `${i.toString().padStart(2, '0')}:00`;
        this.hours.push(hour);
        this.selectedStatus.push('available'); // Initialize all slots as available
      }
    } 
  };
  </script>
  
  <style scoped>
  .text-success {
   background: rgb(75, 233, 133) !important; /* Apply green color to text */
  }
  
  .text-danger {
    background: rgb(226, 105, 65) !important; /* Apply red color to text */
  }
  </style>
  