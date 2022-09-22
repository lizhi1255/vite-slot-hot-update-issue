
<script setup lang='ts'>
const greetingMessage = '无情哈拉哨'

</script>

<template>
  <main>
    <slot :text="greetingMessage" :count="1"></slot>
  </main>
</template>

<style lang="" scoped>

</style>