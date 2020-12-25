<template>
    <div>
      <h1>Dc Heros {{herosCount}}</h1>
      <h1>Dc Heros {{randC}}</h1>
      <h1>Dc Heros {{randC}}</h1>
      <h1>Dc Heros {{randC}}</h1>
      <h1>Dc Heros {{randM()}}</h1>
      <h1>Dc Heros {{randM()}}</h1>
      <h1>Dc Heros {{randM()}}</h1>
      <ul>
        <li v-for="(hero,index) in dcHeros" :key="index">{{index}} {{hero.name}}</li>
      </ul>
      <form 
            @submit.prevent="addHero">
        <input v-model.trim="newHero" placeholder="Type a Hero name">
        <button submit>Add Hero</button>
      </form>
      
    </div>
</template>

<script>
export default {
  computed:{
    herosCount(){
      return this.dcHeros.length;
    },

    randC(){
      return this.dcHeros.length + Math.random();
    }
  },
  methods: {
    addHero(){
      if(this.newHero !== ''){
        this.dcHeros.unshift({name: this.newHero});
        this.newHero='';
      }
      else{
        alert('Filed is empty!');
      }
    },

     randM(){
      return this.dcHeros.length + Math.random();
    }
  },
  data() {
    return {
      isDisabled: true,
      newHero: "",
      dcHeros: [
        {name: "SuperGirl"},
        {name: "BatMan"},
        {name: "SpiderMan"},
        {name: "MonkeyMan"},
        {name: "CaptainPlanet"},
      ]
    }
  },
}
</script>