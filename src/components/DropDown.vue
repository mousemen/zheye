<template>
  <div class="dropdown">
    <a
      class="btn btn-outline-light dropdown-toggle my-2"
      @click.prevent="toggleOpen"
    >
      {{ title }}
    </a>
    <ul class="dropdown-menu" :style="{ display: 'block' }" v-if="isOpen">
      <slot> </slot>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from 'vue'
import useClickOutside from '../hooks/useClickOutside'
export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)
    const dropdownref = ref<null | HTMLElement>(null)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }

    const isclickoutside = useClickOutside(dropdownref)
    watch(isclickoutside, () => {
      if (isOpen.value && isclickoutside.value) {
        isOpen.value = false
      }
    })

    return {
      isOpen,
      toggleOpen,
      dropdownref
    }
  }
})
</script>
