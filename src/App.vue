<template>
  <HTMLComponent :html="html"/>
</template>
<script setup lang="ts">
import HTMLComponent from '@/components/HTMLComponent.vue'
import 'element-plus/theme-chalk/index.css'
import 'element-plus/theme-chalk/display.css'

const html = decodeURIComponent('%3Cp%3ECho%20h%C3%A0m%20s%E1%BB%91%20%3Cscript%20type%3D%22math%2Ftex%22%3Ey%20%3D%20x%5E%7B4%7D%20-%203%20x%5E%7B2%7D%20%2B%202023%3C%2Fscript%3E%20c%C3%B3%20%C4%91%E1%BB%93%20th%E1%BB%8B%20%3Cscript%20type%3D%22math%2Ftex%22%3E%5Cleft(%20C%20%5Cright)%3C%2Fscript%3E.%20%3Cb%3EH%E1%BB%87%20s%E1%BB%91%20g%C3%B3c%3C%2Fb%3E%20%7B%7B%7D%7D%20c%E1%BB%A7a%20%3Ci%20style%3D%22color%3A%20red%3B%22%3Eti%E1%BA%BFp%20tuy%E1%BA%BFn%20%C4%91%E1%BB%93%20th%E1%BB%8B%3C%2Fi%3E%20%3Cscript%20type%3D%22math%2Ftex%22%3E%5Cleft(%20C%20%5Cright)%3C%2Fscript%3E%20t%E1%BA%A1i%20%C4%91i%E1%BB%83m%20%7B%7B%7D%7D%20c%C3%B3%20ho%C3%A0nh%20%C4%91%E1%BB%99%20b%E1%BA%B1ng%20%3Cscript%20type%3D%22math%2Ftex%22%3E-%201%3C%2Fscript%3E%20l%C3%A0%3A%20%7B%7B%7D%7D%3C%2Fp%3E')

</script>

<style lang="scss">
@use "element-plus/theme-chalk/src/index.scss" as *;
@use "element-plus/theme-chalk/src/display.scss" as *;
@import 'katex/dist/katex.min.css';
body {
  background-color: white;
  color: black;
}
</style>
