<template>
    <div>
      <h1>Dc Heros</h1>
      <ul>
        <li v-for="item in dcHeros">{{item.name}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  data() {
    return {
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