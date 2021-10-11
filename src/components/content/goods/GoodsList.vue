<template>
  <div class="goods-list">
    <div v-for="item in goods" class="goods-list-item">
      <img :src="item.show.img" alt="">
      <div class="goods-info">
        <p>{{item.title}}</p>
        <span class="price">{{item.price}}</span>
        <span class="collect">{{item.cfav}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GoodsList",
  props: {
    goods: {
      type: Array,
      default() {
        return []
      }
    }
  }
}
</script>

<style scoped>
  .goods-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 2px;
  }
  .goods-list-item {
    position: relative;
    padding-bottom: 40px;
    width: 48%;
    text-align: center;
  }
  .goods-list-item img {
    width: 100%;
    border-radius: 5px;
  }
  .goods-info {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 5px;
    font-size: 12px;
  }
  .goods-info p {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    margin-bottom: 3px;
  }
  .goods-info .price {
    color: var(--color-high-text);
    padding-right: 20px;
  }
  .goods-info .collect {
    position: relative;
  }
  .goods-info .collect::before {
    content: '';
    position: absolute;
    left: -15px;
    top: -1px;
    width: 14px;
    height: 14px;
    background: url("~assets/img/common/collect.svg") 0 0/14px 14px;
  }
</style>
