<template>
  <div class="detail-bottom-bar">
    <div class="bar-item bar-left">
      <div>
        <i class="icon service"></i>
        <span class="text">客服</span>
      </div>
      <div>
        <i class="icon shop"></i>
        <span class="text">店铺</span>
      </div>
      <div>
        <i class="icon select"></i>
        <span class="text">收藏</span>
      </div>
    </div>
    <div class="bar-item bar-right">
      <div class="cart" @click="addToCart">加入购物车</div>
      <div class="buy">购买</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "DetailBottomBar",
    methods:{
      addToCart(){
        // 点击添加到购物车中
        this.$emit('addToCart')
      }
    }
  }
</script>

<style scoped>
  .detail-bottom-bar{
    position: fixed;
    display: flex;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 11;
    height: 49px;
    background: #f6f6f6;
    text-align: center;
    box-shadow: 0 -1px 1px rgba(100,100,100,.2);
  }
  .bar-item{
    flex: 1;
    display: flex;
  }
  .bar-item>div{
    flex: 1;
  }
  .bar-left .text{
    font-size: 13px;
    position: relative;
    top: -5px;
  }
  .bar-left .icon{
    display: block;
    width: 22px;
    height: 22px;
    margin:10px auto 3px;
    background: url("~assets/img/detail/detail_bottom.png")0 0/100%;
  }
  .bar-left .service{
    background-position: 0 -54px;
  }
  .bar-left .shop{
    background-position: 0 -98px;
  }
  .bar-right{
    font-size: 15px;
    color: #fff;
    line-height: 58px;
  }
  .bar-right .cart{
    background-color: #ffe817;
    color: #333;
  }
  .bar-right .buy{
    background-color: #f69;
  }
</style>
