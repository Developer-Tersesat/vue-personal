<template>
    <div class="slides">
        <h3>slide in here</h3>
        <div class="slides-inner" v-for="slide in slides">
            {{slide}}
        </div>
    </div>
</template>
<script>
export default {
    data : function(){
        slides : [
          {src : 'static/slide-1.png'}
        ]
  }
}
</script>
<style scoped>

</style>