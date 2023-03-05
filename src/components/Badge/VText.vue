<template>
<span class="bg-sky-400 p-2 rounded-full" :class="`color:${textColor}`">{{msg}}</span>
</template>

<script>
export default {
  props:{
    textColor:{
      type:String,
      required:true
    },
    msg:{
      type:String,
      required: false
    }
  },
  name: "VText"
}
</script>

<style scoped>

</style>
