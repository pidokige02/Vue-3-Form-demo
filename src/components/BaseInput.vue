// comment TODO
// Add label prop
// Allow v-modeling ==> bind value and placeholder to the input value via prop.
    // :value="modelValue" // value can be string and number
    // :placeholder="label"
// Bind $attrs
// bind the $attrs object to input by adding v-bind="$attrs” to our input element. ($attrs 은 자식 component 와 공유될 parent prop 인가?)
// With this small change, the input elements will now correctly receive the type binding from the parent, and our CSS classes will be applied.

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
