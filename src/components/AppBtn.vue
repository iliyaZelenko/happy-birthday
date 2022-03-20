<template>
  <div class="btn">
    <slot name="default" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AppBtn'
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
.btn
  display: inline-flex
  align-items: center
  font-size: 25px
  outline: 0
  border: 0
  cursor: pointer
  will-change: box-shadow,transform
  background: radial-gradient( 100% 100% at 100% 0%, #89E5FF 0%, #5468FF 100% )
  box-shadow: 0px 2px 4px rgb(45 35 66 / 40%), 0px 7px 13px -3px rgb(45 35 66 / 30%), inset 0px -3px 0px rgb(58 65 111 / 50%)
  padding: 0 32px
  border-radius: 6px
  color: #fff
  height: 48px
  text-shadow: 0 1px 0 rgb(0 0 0 / 40%)
  transition: box-shadow 0.15s ease,transform 0.15s ease

  :hover
    box-shadow: 0px 4px 8px rgb(45 35 66 / 40%), 0px 7px 13px -3px rgb(45 35 66 / 30%), inset 0px -3px 0px #3c4fe0
    transform: translateY(-2px)

  :active
    box-shadow: inset 0px 3px 7px #3c4fe0
    transform: translateY(2px)
</style>
