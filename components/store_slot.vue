<template>
   <div class="info"> 
      <p class="title"><slot name="title"></slot></p>
      <p class="desc"><slot name="desc"></slot></p>
        
     <button id="ori_2" v-on:click="shop_click('ori', '50', points, 10)" class="buy_button">50g</button>
    </div>
</template>

<script>
    export default {
        name: "store_slot"
    }
</script>

<style scoped>

  .title{margin-top: 5px;}
  .info{margin-left:5px; width: 70%; height: 97px;}
  .buy_button{width:30%; background-color: #ffd8d8; box-shadow: -10px 0px 10px -6px #dd7575;}
  .buy_button:disabled{background-color: #7a2727;}
</style>
