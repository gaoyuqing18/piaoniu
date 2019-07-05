<template>
  <div class="activity-floor-item">
    <a href="javascript:;">
      <div
        class="poster"
        :data-src="movie.poster"
        lazy="loaded"
        :style="{'background-image':'url('+ movie.poster +')'}"
      >
       <div v-if=movie.locationType class="discount-tag">
          <div class="text">
            <span class="num">{{Math.floor(movie.discountRate)}}</span>
            <span class="fraction">.{{(movie.discountRate)*10%10}}</span>
            <span class="unit">折</span>
          </div>
        </div>
        <div v-else class="want-watch">
          <div class="num">{{movie.wantWatchNum}}</div>
          <div class="like"></div>
        </div> 
      </div>

      <div  class="name">{{movie.properName}}</div>
      <div  class="price">
        <span  class="price-num">￥{{movie.lowPrice}}</span>
        <span v-if="movie.locationType" class="price-desc discount-activities">￥{{movie.originPrice}}</span>
        <span v-else class="price-desc">{{qi}}</span>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
     qi: '起',
    };
  },
  props: {
    movie: Object,
    from: String
  }
};
</script>

<style lang="stylus"  scoped>
.activity-floor-item {
  width: 102px;
  margin-right: 10px;
  -ms-flex-negative: 0;
  flex-shrink: 0;
}

.activity-floor-item .poster {
  height: 137px;
  background-position: 50%;
  background-size: cover;
  width: 100%;
  position: relative;
}

.activity-floor-item .name {
  white-space: nowrap;
  margin-top: 7px;
  margin-bottom: 3px;
  color: #262626;
  overflow: hidden;
  text-overflow: ellipsis;
}

.activity-floor-item .price {
  height: 17px;
}

.activity-floor-item .price .price-num {
  color: #ff2661;
  font-size: 12px;
}

.activity-floor-item .price .price-desc {
  font-size: 12px;
  transform: scale(0.8);
  transform-origin: left bottom;
  display: inline-block;
  margin-left: 2px;
  color: #999;
}
.discount-activities  {
    text-decoration: line-through;
}

.activity-floor-item .want-watch {
  background-color: #000;
  background-color: rgba(0, 0, 0, 0.55);
  width: 40px;
  height: 32px;
  position: absolute;
  top: 0;
  left: 1px;
}

.activity-floor-item .want-watch .num {
  line-height: 1.1;
  font-weight: 500;
  font-size: 12px;
  height: 14px;
  color: #fff;
  margin-top: 3px;
  text-align: center;
}

.activity-floor-item .want-watch .like {
  margin: 2px auto;
  width: 10px;
  height: 9px;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url('../assets/styles/xin.png');
}
.discount-tag {
    position: absolute;
    top: -3px;
    left: 2px;
    color: #fff;
    width: 28px;
    height: 30px;
    text-align: center;
    background-image: url(../assets/styles/discount.png);
    background-size: 100%;
}
.discount-tag .text {
    position: relative;
    font-size: 16px;
    width: 100%;
    height: 100%;
}
.discount-tag .text .num {
    font-size: 22px;
    font-weight: 700;
    position: absolute;
    left: 1px;
    top: 0;
}
.discount-tag .text .fraction {
    font-size: 12px;
    position: absolute;
    top: 4px;
    right: 4px;
}
.discount-tag .text .unit {
    font-size: 8px;
    transform: scale(.8);
    transform-origin: left;
    position: absolute;
    bottom: 4px;
    right: 4px;
}
</style>

