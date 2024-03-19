<template>
    <b-calendar v-model="value"  @context="onContext" class="border rounded p-2" locale="fr"></b-calendar>
  </template>
<script>
export default {
  data() {
    return {
      value: '',
      context: null
    }
  },
  methods: {
    onContext(ctx) {
      this.context = ctx
      this.HandelDay()
    },
    HandelDay(){ 
    if(this.value){
        console.log(' this.context  : \n', this.context.selectedFormatted.split(' ')[0])
        this.$emit('HandelSelection', this.context.selectedFormatted.split(' ')[0]);
    }
 }  
 , 

  }
}
</script>
  