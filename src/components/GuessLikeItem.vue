<template>
  <li class="activity" article="[object Object]">
    <div class="main-top">
      <a class="poster-wrap">
        <div v-if="movie.recommendContent.discountRate" class="discount-tag">
          <span class="integer">{{Math.floor(movie.recommendContent.discountRate)}}</span>
          <span class="decimal">.{{(movie.recommendContent.discountRate)*10%10}}</span>
          <span class="text">折</span>
        </div>
        <div class="video-play" style="background-size: 26px 26px; display: none;">
          <video class="video"></video>
        </div>
        <div
          class="poster"
          :data-src="movie.recommendContent.poster"
          lazy="loaded"
          :style="{'background-image': 'url('+ movie.recommendContent.poster +')' }"
        ></div>
      </a>
      <div class="info">
        <div class="title-line">
          <a class="title">
            <span class="city" style>[北京]</span>
            {{movie.recommendContent.properName}}
          </a>
          <div class="activityTag">
            <!---->

            <div v-if="movie.recommendContent.activitySeatMapOpened" class="choose">座</div>
            <div v-if="movie.recommendContent.canBuyEcard" class="eCard">电</div>
          </div>
        </div>
        <div class="time-address">
          <span class="time">{{movie.recommendContent.timeRange}}</span>
          <span class="split">|</span>
          <span class="address">{{movie.recommendContent.venueName}}</span>
        </div>
        <div v-if="movie.recommendContent.rank" class="rank">
          评分&nbsp;
          <span>{{movie.recommendContent.rank}}</span>
        </div>
        <div v-else class="no-rank">暂无评分</div>
        <div class="price-wrap">
          <div>
            <span class="price">{{movie.recommendContent.lowPrice}}</span>
            <span class="qi">元起</span>
          </div>
          <div class="status-text"></div>
        </div>
        <div class="promotion-info">
          <ul></ul>
        </div>
        <div class="light-spot">"{{movie.recommendContent.desc}}"</div>
      </div>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    movie: Object
  }
};
</script>

<style lang="stylus" scoped>
.activity {
  position: relative;
  margin-left: 15px;
  margin-right: 15px;
  background-color: #fff;
  height: 1.75rem;
}

.activity .poster-wrap {
  position: absolute;
  left: 0;
  top: 15px;
}

.activity .main-top {
  min-height: 125px;
  position: relative;
  display: block;
}

.video-play {
  background-repeat: no-repeat;
  position: absolute;
  background-size: 26px 26px;
  background-position: 50% 50%;
  // background-image: url(//static.piaoniu.com/nuxt-static/img/icon-play.23407ce.png);
}

.activity .poster-wrap .poster {
  width: 75px;
  height: 100px;
}

.activity .poster {
  background-size: cover;
  background-position: 50%;
}

.activity .info {
  padding-top: 15px;
  margin-left: 92px;
  border-bottom: 1px solid hsla(0, 0%, 90%, 0.5);
}

.activity .info .title-line {
  display: -ms-flexbox;
  display: flex;
}

.activity .info .title {
  font-size: 15px;
  color: #333;
  max-height: 44px;
  line-height: 22px;
  display: -webkit-box;
  -webkit-line-clamp: 1;
  overflow: hidden;
  text-overflow: ellipsis;
  font-family: Helvetica Neue, Microsoft Yahei, Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans;
  font-weight: 600;
}

.activity .activityTag {
  -ms-flex-negative: 0;
  flex-shrink: 0;
  max-width: 40px;
  margin-left: 4px;
  color: #fff;
}

.activity .eCard, .activity .eCard2 {
  bottom: 12px;
  text-align: center;
  font-size: 10px;
  display: inline-block;
}

.activity .eCard {
  margin-right: 5px;
  border-radius: 2px;
  padding: 1px;
  width: 15px;
  height: 15px;
  background-color: #96a3ff;
  box-sizing: border-box;
}

.activity .choose {
  display: inline-block;
  border-radius: 2px;
  padding: 1px;
  margin-right: 5px;
  bottom: 12px;
  text-align: center;
  font-size: 10px;
  width: 15px;
  height: 15px;
  background-color: #f66b9d;
  box-sizing: border-box;
}

.activity .info .time-address {
  font-size: 12px;
  color: #999;
  margin-top: 9px;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}

.activity .info .time-address .split {
  margin: 0 4px;
}

.activity .info .no-rank, .activity .info .rank {
  font-size: 10px;
  color: #999;
  margin-top: 4px;
  margin-bottom: 16px;
}

.activity .info .rank span {
  font-size: 12px;
  font-weight: 700;
  color: #ffb02e;
}

.activity .info .rank span {
  font-size: 12px;
  font-weight: 700;
  color: #ffb02e;
}

.activity .price-wrap .price {
  position: relative;
  top: 1px;
  color: #ff2661;
  font-size: 18px;
  font-weight: 700;
  margin-right: 4px;
}

.activity .price-wrap .qi, .activity .price-wrap .unit {
  font-size: 10px;
  color: #999;
}

.activity .price-wrap .status-text {
  font-size: 10px;
  color: #999;
  width: 45px;
  line-height: 19px;
  text-align: center;
  background-color: #f0f0f0;
}

.activity .promotion-info {
  margin-bottom: 10px;
}

.activity .light-spot {
  font-size: 12px;
  color: #999;
  padding: 14px 0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
  border-top: 1px solid hsla(0, 0%, 90%, 0.5);
}
.activity .discount-tag .integer {
    position: absolute;
    top: 0;
    left: 1px;
    font-size: 22px;
    font-weight: 700;
    text-align: center;
    color: #fff;
}
.activity .discount-tag .decimal {
    position: absolute;
    top: 4px;
    right: 4px;
    font-size: 12px;
    font-weight: 700;
}
.activity .discount-tag .text {
    position: absolute;
    bottom: 4px;
    right: 4px;
    font-size: 8px;
}
.activity .discount-tag {
    position: absolute;
    top: -3px;
    left: 2px;
    width: 28px;
    height: 30px;
    background-size: 100%;
    text-align: center;
    color: #fff;
    background-image: url(../assets/styles/discount.png);
}
</style>
