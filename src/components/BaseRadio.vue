<template>
  <input
    type="radio"
    :id="uuid"
    :checked="modelValue === value"
    :value="value"
    v-bind="$attrs"
    @change="$emit('update:modelValue', value)"
  />
  <label :for="uuid" v-if="label">{{ label }}</label>
</template>

<script>
import UniqueID from '../features/UniqueID';

export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    },
    value: {
      type: [String, Number],
      required: true
    }
  },
  setup () {
    const uuid = UniqueID().getID()
    return {
      uuid
    }
  }
}
</script>
