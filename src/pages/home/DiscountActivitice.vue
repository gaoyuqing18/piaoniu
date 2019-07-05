<template>
  <div>
    <div class="hot-activities">
      <div class="activity-floor">
        <div class="header">
          <div class="title">折扣专区</div>
          <a href="bj-hot" class="more">全部 ></a>
        </div>
        <div class="activities">
          <!-- 在此处加beterscroll -->
          <div class="wrap">
            <active-floor-item v-for="item in list" :key="item.id" :movie="item">
              <!-- 定义一条数据为movie对象  可以使用 v-bind 来动态传递 prop子组件可以访问这个数据 -->
            </active-floor-item>

            <div class="more">
              <a href @click="handleclick">
                <div class="poster"></div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="da-banner">
      <div>
        <img
          src="https://img.piaoniu.com/banner/b5cbe1866115f85b91f3eca09dcbe1d103d92a5b.jpg"
          style="width: 100%; height: .8328rem;"
        />
      </div>
    </div>
    <a href="/discover/search.html" class="piaoquan">
      <span>更多精彩内容待你发现</span>
      <span class="arrow">></span>
    </a>
  </div>
</template>

<script>
import http from "../../utils/http";
import ActiveFloorItem from "@/components/ActiveFloorItem";
export default {
  data() {
    return {
      list: {} //定义一个list接收请求的数据
    };
  },
  components: {
    ActiveFloorItem
  },

  async mounted() {
    let result = await http.get({
      //?pageIndex=1&pageSize=10
      url: "/api/v1/activities/discount",
      params: {
        pageIndex: 1,
        pageSize: 10
      }
    });
    this.list = result.data;
    console.log(result);
  },

  methods: {
    handleclick() {
      //this.$router.go('https://www.baidu.com/')
      this.$router.go("https://www.baidu.com/");
    }
  }
};
</script>

<style lang="stylus" scoped>
.activity-floor {
  background-color: #fff;
  padding-bottom: 8px;
  padding-top: 32px;
}

.activity-floor .header {
  overflow: hidden;
  padding: 0 14px 16px;
}

.activity-floor .header .title {
  font-weight: 700;
  color: #565656;
  font-size: 18px;
  float: left;
}

.activity-floor .header .more {
  float: right;
  font-size: 14px;
  color: #999;
  height: 17px;
  line-height: 17px;
  padding-right: 10px;
  background-position: 100%;
  background-repeat: no-repeat;
  background-size: 5px 9px;
}

.activity-floor .activities {
  width: 100%;
  overflow-x: scroll;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
}

.activity-floor .activities .wrap {
  padding-left: 14px;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: nowrap;
  flex-wrap: nowrap;
}

.activity-floor .activities .wrap .more {
  display: inline-block;
  -ms-flex-negative: 0;
  flex-shrink: 0;
  width: 116px;
  height: 177px;
  padding-right: 14px;
}

.activity-floor .activities .wrap .more .poster {
  background-size: cover;
  background-image: url('../../assets/styles/more.png');
  height: 137px;
}

.da-banner {
  padding-top: 32px;
  padding-bottom: 8px;
}

.da-banner>div {
  width: 100%;
  background-color: #fff;
}

.da-banner img {
  display: block;
  padding: 0 14px;
}
.piaoquan {
    margin: 24px 14px;
    border-radius: 4px;
    border: 1px solid #f5f5f5;
    color: #262626;
    -ms-flex-pack: center;
    justify-content: center;
    -ms-flex-align: center;
    align-items: center;
    line-height: 40px;
    display: -ms-flexbox;
    display: flex;
    box-sizing: border-box;
}
.piaoquan span.arrow {
    height: 40px;
    width: 7px;
    margin-left: 8px;
    background-size: cover;
}
</style>
