// comment TODO
// Add label prop
// Allow v-modeling ==> bind value and placeholder to the input value via prop.
    // :value="modelValue" // value can be string and number
    // :placeholder="label"
// Bind $attrs
// 
<template>
  <label v-if="label">{{ label }}</label>
  <input
    v-bind="$attrs"
    :value="modelValue"
    :placeholder="label"
    @input="$emit('update:modelValue', $event.target.value)"
    class="field"
  >
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}
</script>
