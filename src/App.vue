<template>
    <div>
      <h1>Dc Heros</h1>
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
  methods: {
    addHero(){
      this.dcHeros.push({name: this.newHero});
      this.newHero='';
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