<template>
    <div class="groceryTab">
        <img :src="grocery.imageurl"/>
          <div class="grdetails">
            <h3>{{ grocery.name }}</h3>
            <a>price: {{ grocery.price }}</a><br/>
            <a>catogery: {{ grocery.catogery }}</a><br/>
            <a>stock status: {{ grocery.stock }}</a>
          </div>
    </div>
</template>
<script>

export default {
    name: 'GroceryTab',
    props:{
        grocery: Object 
    }
}
</script>
<style>
.groceryTab {
      display: grid;
      border: 1px solid black;
      margin: 2px;
      width: 75%;
      margin-left: auto;
      margin-right: auto;
      grid-template-columns: 1fr 1fr;
      grid-template-areas: "grimg" "grdetails";
    }
  
    .groceryTab img{
      grid-area: "grimg";
      width: 150px;
      margin-left: auto;
      margin-right: auto;
    }
    .grdetails{
      grid-area: "grdetails";
    }
</style>