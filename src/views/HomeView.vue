<template>


<div  class="d-flex justify-content-center">
  <b-card no-body class="overflow-hidden" style="max-width: 600px;">
    <b-row no-gutters>
     
      <b-col >
        <b-card-body title="Horizontal Card">
          <b-card-text>
            This is a wider card with supporting text as a natural lead-in to additional content.
            This content is a little bit longer.
          </b-card-text>
        </b-card-body>
      </b-col>
      <b-col >
       <calendar  @HandelSelection="HandelDay"/>
      </b-col>
      <b-col   v-if="Cday" >
          <day  :Cday="Cday" />
      </b-col>
    </b-row> 
  </b-card>
</div>




</template>

<script>
// // @ is an alias to /src
import calendar from '../components/calendar.vue'
import day from '../components/day.vue'

export default {
  name: 'HomeView',
  components: {
    calendar,day
  },
  data(){
    return{
      Cday:'' 
    }
  },
  methods :{
    HandelDay(data){
      // console.log('data : \n',data)
this.Cday=data

// console.log('Cday : \n ',this.Cday) 
    },
  }
,
  mounted() {
//  console.log('Cday : \n ',this.Cday) 
},
 

}
</script>
