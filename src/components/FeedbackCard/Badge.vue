<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <span
    :class="`bg-${classColor}`"
    class="p-2 text-xs font-black text-white uppercase rounded-full">
    {{ label }}
  </span>
</template>

<script>
import { computed } from 'vue'
export default {
  props: {
    type: { type: String, required: true }
  },
  setup (props) {
    const label = computed(() => {
      if (props.type === 'ISSUE') {
        return 'issue'
      }

      if (props.type === 'IDEA') {
        return 'ideia'
      }

      return 'others'
    })

    const classColor = computed(() => {
      if (props.type === 'ISSUE') {
        return 'brand-danger'
      }

      if (props.type === 'IDEA') {
        return 'brand-warning'
      }

      return 'brand-graydark'
    })

    return {
      label,
      classColor
    }
  }
}
</script>
