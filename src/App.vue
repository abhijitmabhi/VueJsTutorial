<template>
    <div>
      <h1>Dc Heros</h1>
      <ul>
        <li v-for="(hero,index) in dcHeros" :key="index">{{index}} {{hero.name}}</li>
      </ul>
      <input v-model.lazy="newHero">
      <button :disabled="isDisabled">Add Hero</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      isDisabled: true,
      newHero: "Aquman",
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