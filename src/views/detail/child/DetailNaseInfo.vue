<template>
  <div class="base-info" v-if="Object.keys(goods).length !== 0">
    <div class="info-title">{{goods.title}}</div>
    <div class="info-price">
      <span class="n-price">{{goods.newPrice}}</span>
      <span class="o-price">{{goods.oldPrice}}</span>
      <span class="discount" v-if="goods.discount">{{goods.discount}}</span>
    </div>
    <div class="info-other">
      <div><span>{{goods.columens[0]}}</span></div>
      <div><span>{{goods.columens[1]}}</span></div>
      <div><span>{{goods.services[goods.services.length-1].name}}</span></div>
    </div>
    <div class="info-service">
      <span class="info-service-item" v-for="index in goods.services.length-1" :key="index">
        <img :src="goods.services[index-1].icon">
        <span>{{goods.services[index-1].name}}</span>
      </span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "DetailNaseInfo",
    props:{
      goods:Object
    }
  }
</script>

<style scoped>
  .base-info{
    margin-top: 15px;
    padding: 0 8px;
    color: #999;
    border-bottom: 5px solid #f2f5f8;
  }
  .info-title{
    color: #222;
  }
  .info-price{
    margin-top: 10px ;
  }
  .info-price .n-price{
    font-size: 24px;
    color: var(--color-high-text);
  }
  .info-price .o-price{
    font-size: 13px;
    margin-left: 5px;
    text-decoration: line-through;
  }
  .info-price .discount{
    font-size: 12px;
    padding: 2px 5px;
    color: #fff;
    background: var(--color-high-text);
    border-radius: 8px;
    margin-left: 5px;
    position: relative;
    top: -8px;
  }
  .info-other{
    display: flex;
    text-align: center;
    margin-top: 12px;
    line-height: 30px;
    font-size: 13px;
    border-bottom: 1px solid rgba(100,100,100,.1);
    /*justify-content: space-between;*/
  }
  .info-other div{
    flex: 1;
  }
  .info-service{
    display: flex;
    justify-content: space-between;
    line-height: 60px;
  }
  .info-service-item img{
    width: 14px;
    height: 14px;
    position: relative;
    top: 2px;
  }
  .info-service-item span{
    font-size: 13px;
    color: #333;
  }
</style>
