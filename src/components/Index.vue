<template>
  <div class="index">
    <el-card class="box-card">
      <div class="parse">
        <el-select v-model="parse_url"
                   clearable
                   placeholder="请选择解析地址"
                   class="el-select-custom">
          <el-option v-for="item in apis"
                     :key="item.value"
                     :label="item.label"
                     :value="item.value">
          </el-option>
        </el-select>
        <el-input class="el-input-custom"
                  v-model="play_url"
                  placeholder="请输入视频地址"></el-input>
        <el-button class="el-button-custom"
                   type="primary"
                   @click="play"
                   round>开始解析</el-button>

        <hr>

        <div class="sites">
          <el-button class="site" type="success">爱奇艺</el-button>
          <el-button class="site" type="info">芒果TV</el-button>
          <el-button class="site" type="warning">腾讯视频</el-button>
          <el-button class="site" type=danger>优酷土豆</el-button>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: "Index",
  data() {
    return {
      parse_url: "",
      play_url: "",
      apis: [
        {
          value: "http://api.baiyug.vip/index.php?url=",
          lable: "http://api.baiyug.vip/index.php?url="
        },
        {
          value: "http://www.82190555.com/index/qqvod.php?url=",
          lable: "http://www.82190555.com/index/qqvod.php?url="
        },
        {
          value: "http://jiexi.071811.cc/jx2.php?url=",
          lable: "http://jiexi.071811.cc/jx2.php?url="
        },
        {
          value: "http://beaacc.com/api.php?url=",
          lable: "http://beaacc.com/api.php?url="
        },
        {
          value: "http://qxkkk.bid/jx/jx.php?url=",
          lable: "http://qxkkk.bid/jx/jx.php?url="
        },
        {
          value: "http://o8ve.cn/1/?url=",
          lable: "http://o8ve.cn/1/?url="
        },
        {
          value: "http://api.xyingyu.com/?url=",
          lable: "http://api.xyingyu.com/?url="
        },
        {
          value: "http://api.greatchina56.com/?url=",
          lable: "http://api.greatchina56.com/?url="
        },
        {
          value: "http://jx.618g.com/?url=",
          lable: "http://jx.618g.com/?url="
        },
        {
          value: "http://jx.iaeec.cn/jx.php/?url=",
          label: "http://jx.iaeec.cn/jx.php/?url="
        },
        {
          value: "https://api.flvsp.com/?url=",
          label: "https://api.flvsp.com/?url="
        },
        {
          value: "http://2gty.com/apiurl/yun.php?url=",
          label: "http://2gty.com/apiurl/yun.php?url="
        },
        {
          value: "http://v.2gty.com/apiurl/yun.php?url=",
          label: "http://v.2gty.com/apiurl/yun.php?url="
        }
      ]
    };
  },
  methods: {
    play() {
      if (!this.parse_url || !this.play_url) {
        this.$message.error("请选择解析地址，并输入视频地址！");
        return;
      }
      if (!/^http.*$/.test(this.play_url)) {
        this.$message.error("视频地址不正确！");
        return;
      }

      window.open(this.parse_url + this.play_url)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box-card {
  width: 80%;
  margin: auto;
  margin-top: 15vh;
  height: 65vh;
}
.parse {
  margin: 0px;
}
.el-select-custom,
.el-input-custom,
.el-button-custom {
  display: block;
  width: 75%;
  margin: auto;
  margin-top: 30px;
}

hr {
  border: none;
  border-top: 1px solid #eee;
  margin-bottom: 60px;
  margin-top: 60px;
  width: 90%;
}
.site {
  margin-top: 5px;
}
</style>
