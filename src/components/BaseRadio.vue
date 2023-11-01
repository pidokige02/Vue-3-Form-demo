<template>
  <input
      type="radio"
      :checked="modelValue === value"
      :value="value"
      v-bind="$attrs"
      @change="$emit('update:modelValue', value)"
    />
  <label v-if="label">{{ label }}</label>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: { // comment : contains user's preferred value from the radio button group
      type: [String, Number],
      default: ''
    },
    value: {    // comment : contains value that attached to this component (ex : dog or cat)
      type: [String, Number],
      required: true
    }
  }
}
</script>
