<template>
  <div class="comboDiv">
    <h1>Attack type:</h1>
    <TypeSelector v-model="attack"></TypeSelector>
  </div>

  <div class="comboDiv">
    <h1>Defense type:</h1>
    <TypeSelector v-model="defense1"></TypeSelector>
  </div>

  <div class="comboDiv" v-if="defense1 != 1">
    <h1>Defense type 2:</h1>
    <TypeSelector v-model="defense2"></TypeSelector>
  </div>
</template>

<script>
import TemTemTypes from './Assets/Types.json'
import TypeSelector from "@/components/TypeSelector";
import {ref} from "vue";

export default {
  name: 'App',
  temtemTypes: TemTemTypes,
  components: {
    TypeSelector,
  },
  props:{
    temtemTypes: TemTemTypes,
  },
  setup() {
    const attack = ref(1);
    const defense1 = ref(1);
    const defense2 = ref(1);
    return {
      attack,
      defense1,
      defense2,
    };
  },
};
</script>

<style>
#app {
  display: flex;
  min-height: 100vh;
  min-width: 100vw;
  justify-content: space-around;
  align-items: center;
}

body {
  margin: 0px;
}

.comboDiv {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}
</style>
