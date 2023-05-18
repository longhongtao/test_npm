<template>
  <div :class="{loading:loading}">
    <div></div>
    <div></div>
    <div></div>
</div>
</template>

<script>
export default {
    props:{
        loading:{
            type:Boolean,
            default:false
        }
    },

}
</script>

<style lang="scss" scoped>
@import url('../css/loading.css');

</style>