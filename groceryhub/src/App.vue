<script>
import appHeading from './components/Heading.vue';
import groceryviewer  from './components/GroceryViewer.vue';

export default {
  name: 'App',
  components: {
   
    appHeading,groceryviewer
  },
  data(){
    return {
      grocerylist: []
    }
  },
  methods:{
    async fetchgroceries(){
      const res = await fetch('https://groceryhub-backend.onrender.com/api');
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created(){
      this.grocerylist = await this.fetchgroceries();
  }
}
</script>

<template>
  <appHeading/>
  <div v-for="grocery in grocerylist" :key="grocery.id">
    <groceryviewer :groceries="grocery"/>
         
         
       </div>
</template>