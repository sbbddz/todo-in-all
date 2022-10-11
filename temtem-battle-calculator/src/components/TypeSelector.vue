<template>
  <div class="input-group group-sm mb-2">
    <select
        class="form-control"
        :value="modelValue"
        @change="$emit('update:modelValue', $event.target.value)"
    >
      <option v-for="type in typesArray" :value="type">
        {{ type }}
      </option>
    </select>
  </div>
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
select {
  background: #f9f9f9;
  padding: 0.5rem;
  border-radius: 1rem;
  font-size: 1rem;
}

</style>