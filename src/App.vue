<template>
<AppHeader/>
<div class="w-full flex">
  <DcHeroes/>
</div>
<div class="w-full flex">
  <Calendar/>
</div>

</template>

<script>
import AppHeader from "./components/AppHeader";
import DcHeroes from "./components/DcHeroes";
import Calendar from "./components/Calendar";

export default {
  components: {
    AppHeader,
    DcHeroes,
    Calendar
  },
  
}
</script>