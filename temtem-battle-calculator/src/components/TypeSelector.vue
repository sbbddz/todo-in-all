<template>
  <fieldset>
    <div class="input-group group-sm mb-2">
      <span class="input-group-text" v-html="label"></span>
      <select
          class="form-control"
          :value="modelValue"
          @change="$emit('update:modelValue', $event.target.value)"
      >
        <option v-for="type in typesArray" :value="type">
          {{type}}
        </option>
      </select>
    </div>
    <p>SelectedField model value: {{ modelValue }}</p>
  </fieldset>
</template>

<script>
export default {
  name: "TypeSelector",
  data() {
    return {
      typesArray: [
        "not selected",
        "normal",
        "fire",
        "water",
        "nature",
        "electric",
        "earth",
        "mental",
        "wind",
        "digital",
        "melee",
        "cristal",
        "toxic"
      ]
    }
  },
  props: {
    modelValue: String,
  },
};
</script>


<style scoped>

</style>