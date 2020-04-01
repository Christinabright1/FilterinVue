<template>
  <div>
  <h2>Filter and mixing</h2>
  <p>{{text | toUppercase}}</p>
  <input v-model="filtertext">
  <ul>
    <li v-for="fruit in  filterfruits">{{fruit}}</li>
  </ul>
  </div>
</template>

<script>

export default {
    data(){
      return {
        text: 'Hello there',
        fruits: ['Banana', 'kiwi','Anana','Mango'],
        filtertext: ''
      }
    },
    computed: {
      filterfruits(){
    return this.fruits.filter((element) => {
      return element.toLowerCase().match(this.filtertext.toLowerCase());
    })
      }
    }
    
    
}
</script>

<style>

</style>
