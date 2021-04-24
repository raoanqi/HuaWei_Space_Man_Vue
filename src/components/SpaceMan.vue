<template>
  <div id="container">
    <div class="h-one" :class="hOne"></div>
    <div class="h-two" :class="hTwo"></div>
    <div class="react"></div>
    <div class="m-one" :class="mOne"></div>
    <div class="m-two" :class="mTwo"></div>
    <div class="s-one" :class="sOne"></div>
    <div class="s-two" :class="sTwo"></div>
    <div class="man"></div>
    <div class="date">
      {{ YMD }}
    </div>
  </div>
</template>

<script>
export default {
  name: "SpaceMan",
  data() {
    return {
      fullDateInfo: [],
      YMD: null
    }
  },
  computed: {
    hOne() {
      return this.numTransUtil(this.fullDateInfo[0])
    },
    hTwo() {
      return this.numTransUtil(this.fullDateInfo[1])
    },
    mOne() {
      return this.numTransUtil(this.fullDateInfo[2])
    },
    mTwo() {
      return this.numTransUtil(this.fullDateInfo[3])
    },
    sOne() {
      return this.numTransUtil(this.fullDateInfo[4])
    },
    sTwo() {
      return this.numTransUtil(this.fullDateInfo[5])
    }
  },
  methods: {
    numTransUtil(num) {
      switch (num) {
        case 0:
          return 'bg-img-0'
        case 1:
          return 'bg-img-1'
        case 2:
          return 'bg-img-2'
        case 3:
          return 'bg-img-3'
        case 4:
          return 'bg-img-4'
        case 5:
          return 'bg-img-5'
        case 6:
          return 'bg-img-6'
        case 7:
          return 'bg-img-7'
        case 8:
          return 'bg-img-8'
        case 9:
          return 'bg-img-9'
        default:
          return 'bg-img-8'
      }
    },
    //  获取年月日
    getYMD() {
      let dateObj = new Date()
      this.YMD = `${dateObj.getFullYear()}年${dateObj.getMonth() + 1}月${dateObj.getDate()}日`
    },
    //  获取时分秒信息
    getFullDateInfo() {
      setInterval(() => {
        let dateObj = new Date()
        this.fullDateInfo = [
          Math.floor(dateObj.getHours() / 10),
          Math.floor(dateObj.getHours() % 10),
          Math.floor(dateObj.getMinutes() / 10),
          Math.floor(dateObj.getMinutes() % 10),
          Math.floor(dateObj.getSeconds() / 10),
          Math.floor(dateObj.getSeconds() % 10)
        ]
      }, 1000)
    }
  },
  created() {
    this.getFullDateInfo()
    this.getYMD()
  }
}
</script>

<style lang="less">
// 外侧圆形容器
#container {
  position: relative;
  width: 640px;
  height: 640px;
  background-image: url('../assets/image/ring.svg');
  background-repeat: no-repeat;
  background-size: 100%;
  margin: auto;

  .bg-img-0 {
    background-image: url("../assets/image/0.svg");
  }

  .bg-img-1 {
    background-image: url("../assets/image/1.svg");
  }

  .bg-img-2 {
    background-image: url("../assets/image/2.svg");
  }

  .bg-img-3 {
    background-image: url("../assets/image/3.svg");
  }

  .bg-img-4 {
    background-image: url("../assets/image/4.svg");
  }

  .bg-img-5 {
    background-image: url("../assets/image/5.svg");
  }

  .bg-img-6 {
    background-image: url("../assets/image/6.svg");
  }

  .bg-img-7 {
    background-image: url("../assets/image/7.svg");
  }

  .bg-img-8 {
    background-image: url("../assets/image/8.svg");
  }

  .bg-img-9 {
    background-image: url("../assets/image/9.svg");
  }

  // 小时的第一位
  .h-one {
    position: absolute;
    width: 100px;
    height: 100px;
    background-repeat: no-repeat;
    background-size: 100%;
    left: 140px;
    top: 170px;
  }

  //  小时的第二位
  .h-two {
    position: absolute;
    width: 100px;
    height: 100px;
    background-repeat: no-repeat;
    background-size: 100%;
    left: 200px;
    top: 170px;
  }

  //  时间中间的点
  .react {
    position: absolute;
    width: 30px;
    height: 80px;
    left: 275px;
    top: 180px;
    background-image: url('../assets/image/rect.svg');
    background-size: 40px 40px;
  }

  //  分钟第一位
  .m-one {
    position: absolute;
    width: 100px;
    height: 100px;
    left: 290px;
    top: 170px;
    background-repeat: no-repeat;
    background-size: 100%;
  }

  //  分钟第二位
  .m-two {
    position: absolute;
    width: 100px;
    height: 100px;
    left: 350px;
    top: 170px;
    background-repeat: no-repeat;
    background-size: 100%;
  }

  //  秒钟第一位
  .s-one {
    position: absolute;
    width: 60px;
    height: 60px;
    left: 430px;
    top: 207px;
    background-repeat: no-repeat;
    background-size: 100%;
  }

  //  秒钟第二位
  .s-two {
    position: absolute;
    width: 60px;
    height: 60px;
    left: 470px;
    top: 207px;
    background-repeat: no-repeat;
    background-size: 100%;
  }

  //  太空人
  .man {
    position: absolute;
    width: 150px;
    height: 150px;
    left: 250px;
    top: 280px;
    background-image: url('../assets/image/human.gif');
    background-repeat: no-repeat;
    background-size: 100%;
  }

  //  日期
  .date {
    position: absolute;
    width: 160px;
    height: 30px;
    left: 415px;
    top: 345px;
    font-size: 20px;
    text-align: center;
  }
}
</style>