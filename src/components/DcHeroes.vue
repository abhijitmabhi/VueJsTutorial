<template>
    <div class="m-auto">
      <h1 class="text-center text-5xl">Dc Heros {{herosCount}}</h1>
      <ul class="my-5">
        <li class="flex justify-between" v-for="(hero,index) in dcHeros" :key="hero.name">
          <div>{{index}} {{hero.name}}</div>
          <button class="border rounded bg-red-300" @click="remove(index)"> X </button>
        </li>
      </ul>
      <form class="mt-10"
            @submit.prevent="addHero">
        <input class="border rounded" v-model.trim="newHero" placeholder="Type a Hero name">
        <button class="border rounded bg-green-600" submit>Add Hero</button>
      </form>
      <!-- <button @click="setFullName">Set FullName</button> -->
    </div>
</template>

<script>
export default {

    computed:{
    herosCount(){
      return this.dcHeros.length;
    },

    fullName: {
      get(){
        return `${this.firstName} ${this.lastName}`;
      } ,
      set(fullName){
        const values = fullName.split(" ");
        this.firstName = values[0];
        this.lastName = values[1];
      }
       
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

    setFullName(){
      this.fullName = "Ahsan Kabir";
    },

    remove(index){
      this.dcHeros = this.dcHeros.filter((hero, i) => i!=index );
    }
  },
  data() {
    return {
      firstName: "Abhijit M.",
      lastName: "Abhi",
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

<style>

</style>