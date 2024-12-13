<template>
        <div v-for="grocery in groceries.groceries" :key="grocery.id">
         
          <GroceryTab :grocery="grocery"/>
          
        </div>
      
  </template>
  
  <script>
import GroceryTab from './GroceryTab.vue';

  
  export default {
    name: 'GroceryViewer',
    components:{
      GroceryTab
    },
    props:{
      groceries: Array
    }
  }
  </script>
  
  <style>
    
  </style>