<template>
  <div class="content" @click="clickHandle">
    <div class="header">
      <div class="my-container">
        <div class="location">
          <img
            class="img-position"
            src="https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/location.png"
          />
          <p>长沙中电软件园</p>
          <img class="img-more" :src="imgMoreUrl" />
        </div>
        <div class="search">
          <img
            class="img-search"
            src="https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/search.png"
          />
          <p class="p-search">曼熊披萨 满28减12</p>
        </div>
        <div class="header-item">
          <ul class="ul-header-item">
            <li class="li-header-item" v-for="hi in headerItem" v-bind:key="hi.id">
              <div class="header-item-content">
                <img class="img-item" :src="hi.itemUrl" />
                <p class="p-header-item">{{ hi.title }}</p>
              </div>
            </li>
          </ul>
        </div>

        <div class="optimal">
          <div class="optimal-top">
            <p class="p-optimal">为你优选</p>
            <div class="optimal-top-more">
              <p class="p-more">更多</p>
              <img class="img-more" :src="imgMoreUrl" />
            </div>
          </div>
          <div class="optimal-content">
            <ul class="ul-optimal-content">
              <li class="li-optimal-content" v-for="oi in optimalItem" :key="oi.id">
                <div>
                  <img class="img-optimal" :src="oi.imgUrl" />
                  <p class="p-optimal-title">{{ oi.title }}</p>
                  <p class="p-optimal-desc">{{ oi.desc }}</p>
                </div>
              </li>
            </ul>
          </div>
        </div>

        <div class="test-swiper">
          <swiper
            class="swiper"
            :indicator-dots="indicatorDots"
            :autoplay="autoplay"
            :interval="interval"
            :duration="duration"
          >
            <block v-for="(item, index) in imgUrls" :index="index" :key="item.key">
              <swiper-item>
                <image :src="item" class="slide-image" />
              </swiper-item>
            </block>
          </swiper>
        </div>

        <div class="test" v-for="(ss, index1) in storeSwiper" :key="ss.id">
          <img class="img-swiper-item-test" :src="ss.backgroundUrl" />
          <div class="img-swiper-item-content">
            <div class="swiper-item-title">
              <img class="img-test" :src="ss.storeUrl" />
              <div class="item-title">
                <p class="p-item-title">{{ ss.storeName }}</p>
                <div class="coupon">
                  <p class="p-coupon" v-for="ssc in ss.coupon" :key="ssc.key">{{ ssc }}</p>
                </div>
              </div>
            </div>

            <p class="p-swiper-item-desc">{{ ss.desc }}</p>

            <div class="test-menu">
              <div class="food" v-for="ssf in ss.food" :key="ssf.id">
                <img class="img-food" :src="ssf.foodUrl" />
                <div class="price">
                  <p class="now-price">{{ ssf.nowPrice }}</p>
                  <p class="del-price">{{ ssf.delPrice }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- <div class="nearby-item">
          <p class="p-nearby-item">附近商家</p>
        </div> -->
      </div>
    </div>

    <!-- <p v-if="test.length < 1" style="color: #000;margin-top: 20rpx">加载中。。。</p>
    <div v-else>
      <p v-for="t in test" :key="t.id">
        <span>{{ t.completed }}</span>---
        <span>{{ t.id }}</span>---
        <span>{{ t.title }}</span>---
        <span>{{ t.userId }}</span>
      </p>
    </div> -->
  </div>
</template>

<script>
import card from "@/components/card";

export default {
  data() {
    return {
      storeSwiper: [
        {
          backgroundUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
          storeUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/windows-fill.png",
          storeName: "杂粮粥（西湖店）",
          coupon: ["25减10", "25减10", "25减10", "25减10"],
          desc: "月销万单谷物轻粥蔬粥来了",
          food: [
            {
              foodUrl:
                "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
              nowPrice: "$19.9",
              delPrice: "$29.9"
            },
            {
              foodUrl:
                "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
              nowPrice: "$19.9",
              delPrice: "$29.9"
            },
            {
              foodUrl:
                "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
              nowPrice: "$19.9",
              delPrice: "$29.9"
            }
          ]
        }
      ],
      imgUrls: [
        "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
        "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg",
        "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
      ],
      indicatorDots: false,
      autoplay: true,
      interval: 5000,
      duration: 1000,

      optimalItem: [
        {
          title: "叫了只炸鸡",
          desc: "根据你看过的店推荐",
          imgUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
        },
        {
          title: "叫了只炸鸡",
          desc: "根据你看过的店推荐",
          imgUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
        },
        {
          title: "叫了只炸鸡",
          desc: "根据你看过的店推荐",
          imgUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
        },
        {
          title: "叫了只炸鸡",
          desc: "根据你看过的店推荐",
          imgUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
        },
        {
          title: "叫了只炸鸡",
          desc: "根据你看过的店推荐",
          imgUrl:
            "https://www.starbucks.com.cn/assets/images/featured/2019summer/homepage-mooncake.jpg"
        }
      ],
      imgMoreUrl:
        "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/right.png",
      headerItem: [
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        },
        {
          title: "美食",
          itemUrl:
            "https://raw.githubusercontent.com/w112452258/w112452258.github.io/master/img/alipay-circle-fill.png"
        }
      ],
      motto: "Hello miniprograme",
      userInfo: {
        nickName: "mpvue",
        avatarUrl: "http://mpvue.com/assets/logo.png"
      },

      test: []
    };
  },

  components: {
    card
  },

  created() {
    console.log(this.test);
    let _this = this;
    wx.request({
      url: "https://jsonplaceholder.typicode.com/todos", //仅为示例，并非真实的接口地址
      data: {
        // id: '',
      },
      header: {
        "content-type": "application/json" // 默认值
      },
      success(res) {
        console.log(res.data);
        _this.test = res.data;
      }
    });
  },

  methods: {
    bindViewTap() {
      const url = "../logs/main";
      if (mpvuePlatform === "wx") {
        mpvue.switchTab({ url });
      } else {
        mpvue.navigateTo({ url });
      }
    },
    clickHandle(ev) {
      console.log("clickHandle:", ev);
      // throw {message: 'custom test'}
    }
  }
};
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}

.header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.my-container {
  width: 95%;
  /* background-color: aqua; */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  /* justify-content: flex-start;
  align-items: flex-start; */
}

.location {
  height: 40rpx;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  /* background-color: antiquewhite; */
}

.img-position {
  width: 20px;
  height: 20px;
}

.img-more {
  margin: 0 3px;
  width: 10px;
  height: 10px;
}

.search {
  width: 100%;
  height: 60rpx;
  background-color: #dadada;
  /* border: 1px solid #999999; */
  border-radius: 10rpx;
  margin-top: 20rpx;
  display: flex;
  align-items: center;
}

.img-search {
  width: 20px;
  height: 20px;
  margin-left: 5px;
}

.p-search {
  font-size: 12px;
  color: #666666;
  margin-left: 5px;
}

.header-item {
  margin: 10px 0;
}

.ul-header-item {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.header-item-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.img-item {
  width: 50px;
  height: 50px;
  margin: 5px 10px;
}

.p-header-item {
  font-size: 10px;
  margin-top: -4px;
}

.optimal {
  width: 100%;
  margin: 20px 0;
}

.optimal-top {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.optimal-top-more {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.p-optimal {
  font-size: 18px;
  letter-spacing: 1px;
}

.p-more {
  font-size: 12px;
  color: #666666;
  /* letter-spacing: 1px; */
}

.optimal-content {
  margin: 10px 0;
}

.ul-optimal-content {
  height: 100px;
  /* background-color: aqua; */
  display: flex;
  flex-wrap: no-wrap;
  overflow-x: scroll;
}

.ul-optimal-content::-webkit-scrollbar {
  display: none;
}

.li-optimal-content {
  margin: 0 3px;
}

.img-optimal {
  width: 130px;
  height: 60px;
  border-radius: 5px;
}

.p-optimal-title {
  font-size: 12px;
  color: #666666;
}

.p-optimal-desc {
  font-size: 10px;
  color: #dadada;
}

.test-swiper {
  width: 100%;
  height: 80px;
  /* height: 500px;
  background-color: aqua; */
  /* background-color: aqua; */
}

.swiper {
  display: flex;
  justify-content: center;
  align-items: center;
}

.slide-image {
  width: calc(100% - 2px);
  height: 80px;
  margin: 0 1px;
}

.img-swiper-item {
  /* width: calc( 100% - 20px ); */
  width: 100%;
  height: 60px;
  margin: 0;
}

.nearby-item {
  margin-top: -50px;
}

.p-nearby-item {
  font-size: 20px;
}

.test {
  position: relative;
  width: 100%;
  height: 220px;
  /* position: relative; */
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  /* background-color: red; */
  border: 1px solid #cccccc;
  border-radius: 5px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
}

.img-swiper-item-test {
  width: 100%;
  height: 70px;
  border-radius: 5px 5px 0 0;
}

.img-swiper-item-content {
  width: 100%;
  height: 50px;
  position: absolute;
  top: 35px;
  left: 8rpx;
}

.swiper-item-title {
  display: flex;
  justify-content: flex-start;
}

.img-test {
  width: 50px;
  height: 50px;
}

.item-title {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 5px;
}

.coupon {
  display: flex;
  flex-direction: row;
}

.p-item-title {
  font-size: 14px;
}

.p-coupon {
  background-color: rgb(255, 89, 89);
  color: #ffffff;
  font-size: 10px;
  margin-right: 5px;
  padding: 0 5rpx;
}

.p-swiper-item-desc {
  font-size: 18px;
  font-weight: 600;
}

.test-menu {
  width: calc(100% - 8px);
  display: flex;
  justify-content: space-between;
  /* background-color: red */
}

.food {
  margin-top: 10px;
}

.img-food {
  width: 110px;
  height: 80px;
  border-radius: 3px;
}

.price {
  display: flex;
}

.now-price {
  color: red;
  font-size: 12px;
  margin-left: 3px;
}

.del-price {
  font-size: 10px;
  margin-left: 5px;
  color: #b0b0b0;
  text-decoration: line-through;
}
</style>
