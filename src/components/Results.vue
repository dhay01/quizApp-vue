<script>
export default {
  props:["results", "totalCorrect"],
  computed:{
    resultIndex() {
        let index = 1;
        this.results.forEach((e,i)=>{
          if(e.min<=this.totalCorrect && e.max>= this.totalCorrect){
              index = i;
          }
        });
        return index;
      },
      },
}
</script>

<template>
  <div class="result">
    <div class="title">{{results[resultIndex].title}}</div>
    <div class="desc">
      {{results[resultIndex].desc}}
    </div>
  </div>
</template>

<style>

</style>