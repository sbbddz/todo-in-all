<template>
  <div class="comboDiv">
    <h1>Attack type</h1>
    <TypeSelector @change="changes()" v-model="attack"></TypeSelector>
  </div>

  <div class="comboDiv">
    <h1>Defense type</h1>
    <TypeSelector @change="changes()" v-model="defense1"></TypeSelector>
  </div>

  <div class="comboDiv" v-if="defense1 != 1">
    <h1>Defense type 2</h1>
    <TypeSelector @change="changes()" v-model="defense2"></TypeSelector>
  </div>

  <div class="comboDiv" v-if="result != 0">
    <h1>Result:</h1>
    <p class="result">{{result}}</p>
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
    const result = 1;
    return {
      attack,
      defense1,
      defense2,
      result,
    };
  },
  methods:{
    changes() {
      if (this.defense2 != 1) {
        this.result = 1 * this.$options.temtemTypes[this.attack][this.defense1] * this.$options.temtemTypes[this.attack][this.defense2]
      }
    }
  }
};
</script>

<style>
#app {
  display: flex;
  min-height: 100vh;
  min-width: 100vw;
  justify-content: space-around;
  align-items: center;
  color: #ffffff;
}

body {
  margin: 0px;
  background: #343434;
}

.comboDiv {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}

.result {
  font-size: 1rem;
  font-weight: 1000;
}
</style>
