<template>
    <div class="container mx-auto">
      <h1>Dc Heros {{herosCount}}</h1>
      <ul>
        <li v-for="(hero,index) in dcHeros" :key="hero.name">
          <div>{{index}} {{hero.name}}<button @click="remove(index)">x</button></div>
          <input>
        </li>
      </ul>
      <form 
            @submit.prevent="addHero">
        <input v-model.trim="newHero" placeholder="Type a Hero name">
        <button submit>Add Hero</button>
      </form>
      <button @click="setFullName">Set FullName</button>
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