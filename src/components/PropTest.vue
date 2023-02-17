<template>
  <div>{{ name.message }}</div>
</template>

<script setup lang='ts'>
const name =  defineProps<{message:boolean}>()
console.log(name);

    
 
</script>
<style scoped lang='less'>
</style>