<template>
    <div>
      <h1>Dc Heros</h1>
      <ul>
        <li v-for="(hero,index) in dcHeros" :key="index">{{index}} {{hero.name}}</li>
      </ul>
      <form 
            @submit.prevent="
            dcHeros.push({name: newHero});
            newHero=''
            ">
        <input v-model.trim="newHero">
        <button submit>Add Hero</button>
      </form>
      
    </div>
</template>

<script>
export default {
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