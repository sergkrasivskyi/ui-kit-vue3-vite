<template>
  <div class="flow">
    <h1 class="heading-1">
      Buttons
    </h1>
    <h2 class="heading-2">
      Color
    </h2>
    <Button :is="typeButton" href="#">Primary</Button>
    <Button color="primary">Primary</Button>
    <Button color="accent">Accent</Button>
    <h2 class="heading-2">
      Rounded
    </h2>
    <Button color="primary" :rounded="true">Primary</Button>
    <Button color="primary" :outlined="true">Accent</Button>
  </div>

</template>
<script setup>
import Button from '@/components/Button.vue'
</script>
<style lang="scss" scoped>
:where(.flow :not(:first-child)) {
  margin-right: 1rem;
  margin-top: 1rem;
}
</style>