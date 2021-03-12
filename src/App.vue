<template>
  <div id="app">

    <h1>{{title}}</h1>

    <input v-model="searchItem" type="text" placeholder="Search">

    <ul>
      <li v-for="(item, index) in filteredItems" :key="index">{{item}}</li>
    </ul>

  </div>
</template>

<script>
export default {
  data() {
    return{
      title: 'Масивный масив',
      searchItem: '',
      items:['BMW','Honda','audi','orange','lemon','pineapple','iron','zinc','copper']
    }
  },
  computed:{
    filteredItems() {
      return this.items.filter(item => {
        return item.toUpperCase().indexOf(this.searchItem.toUpperCase()) !==   -1
      })
    }
  }
}
</script>