<template>
  <h1>DC Heros : {{herosCount}}</h1>
  <ul>
    <li v-for="(hero, index) in dcHeros" :key="index">{{ hero.name}}</li>
  </ul>
  <form @submit.prevent="addHero()">
    <input v-model="newHero" placeholder="Type Hero Name">
    <button type="submit">Add Hero</button>
  </form>
</template>

<script>
export default {
  computed:{
    herosCount(){
      return this.dcHeros.length;
    }
  },
  methods:{
    addHero(){
      if(this.newHero != ""){
        this.dcHeros.push( {name: this.newHero} ); 
        this.newHero='';
      }
    },
  },
  data() {
    return {
      isDisabled: true,
      newHero: "Aquaman",
      dcHeros: [
        {name: "SuperGirl"}, 
        {name: "Flash"}, 
        {name: "Arrows"}, 
        {name: "Batman"}, 
        {name: "SuperMan"},
      ],
    }
  },
}
</script>