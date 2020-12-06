<template>
  <li class="dropdown-toggle-split" :class="{ 'is-disabled': disabled }">
    <slot></slot>
  </li>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'DropdownItem',
  props: {
    disabled: {
      type: Boolean,
      default: false
    }
  }
})
</script>

<style>
.is-disabled * {
  color: #757575;
  pointer-events: none; /** 该属性指定在什么情况下 (如果有) 某个特定的图形元素可以成为鼠标事件的 target。 */
  background: transparent;
}
</style>
