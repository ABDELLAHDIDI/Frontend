<template>


<div  class="d-flex justify-content-center">
  <b-card no-body class="overflow-hidden" style="max-width: 600px;">
    <b-row no-gutters> 
      <b-col >
        <b-card-img src="image.png" alt="Image" class="rounded-circle"></b-card-img>
        <b-card-body title="DIDI ABDELLAH">
          <b-card-text>
            anesthésiologie <br/>
            Tanger , Morocco
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
// import imageUrl from '@/assets/image.png';

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
// console.log('Image URL:', imageUrl);
},
 

}
</script>
