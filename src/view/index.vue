<template>
  <div id="indexPage">
    <!--文本内容-->
    <div class="indexContent container">
      <p class="prompt"><span>公共：</span>防止网站域名失效，请加我们微信公众号“一一影院”请网友收藏！很好记！感谢各位网友的支持！</p>
      <!--section-->
      <!--精品推荐电影-->
      <div class="section1 clearFix">
        <div class="articleLeft excellentMovie fl">
          <el-tabs v-model="activeName" @tab-click="handleClick">
            <el-tab-pane label="精品电影推荐" name="first" disabled>精品电影推荐</el-tab-pane>
            <el-tab-pane label="电影" name="second">
              <div class="cellBox">
                <commonDiv :resourceUrl = "moviePage"></commonDiv>
              </div>
            </el-tab-pane>
            <el-tab-pane label="电视剧" name="third">
              <div class="cellBox">
                <commonDiv></commonDiv>
              </div>
            </el-tab-pane>
            <el-tab-pane label="综艺" name="fourth">
              <div class="cellBox">
                <commonDiv></commonDiv>
              </div>
            </el-tab-pane>
            <el-tab-pane label="动漫" name="fifth">
              <div class="cellBox">
                <commonDiv></commonDiv>
              </div>
            </el-tab-pane>
          </el-tabs>
        </div>
        <div class="articleRight updateMovie fr">
          <resourcesDiv :resourceUrl = "resourceUrl"></resourcesDiv>
        </div>

      </div>
      <div class="section2 clearFix">
        <div class="articleLeft fl">
          <contentListDiv :resourceUrl = "contentUrl"></contentListDiv>
        </div>
        <div class="articleRight fr">
          <resourcesDiv :resourceUrl = "resourceUrl"></resourcesDiv>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import commonDiv from '@/components/commonIndex'     //电影模块
import resourcesDiv from '@/components/resourcesList'
import contentListDiv from '@/components/contentList'
export default {
  name:"indexPage",
  data(){
    return{
      activeName:"second",
      contentUrl:{"url":"../../static/data/contentList1.json","fuTitle":'2017年最佳影片'},
      resourceUrl:{"url":"../../static/data/resourcesList1.json","isFirst":true,"updateNum":1,"fuTitle":'今日更新资源'},
      moviePage:{"url":"../../static/data/comMovie.json"},
      data:[{},{},{},{},{},{}]
    }
  },
  components:{
    commonDiv,
    resourcesDiv,
    contentListDiv
  },
  methods:{
    handleClick(tab, event) {
      console.log(tab, event);
    }
  }
}
</script>

<style lang="less">
#indexPage {
  .indexContent{
    width:100%;
    p.prompt{
      overflow: hidden;
      line-height: 40px;
      height: 40px;
      border: 1px solid #EDCE7B;
      margin: 15px 0;
      background-color: #FFFFEA;
      color: #000000;
      position: relative;
      font-size: 13px;
      text-align: center;
      span{
        color: red;
      }
    }
  .section1{
    width: 100%;
    background: #fff;
    .articleLeft{
      width: 785px;
      height: 610px;
      overflow: hidden;
      border: 1px solid #EDEDED;
    }
    .articleRight{
      width: 300px;
      height: 610px;
      /*overflow: hidden;*/
    }
  }
  .section2{
    margin-top: 30px;
  }
  }
  /*margin-top: 60px;*/
}
.is-disabled{
  text-indent: 20px;
  border-left: 6px solid #16CF88;
  font-weight: 400;
  font-size: 16px;
  color: #15CF87 !important;
}
.el-tabs__item.is-active{
  color: #15CF87 !important;
  border-color: #15CF87 !important;
}
.el-tabs__item:hover{
  color: #15CF87 !important;
}
.el-tabs__active-bar{
  background-color: #16CF88;
  width: 40px !important;
}
/*公共样式*/
/*.articleLeft{*/
  /**/
/*}*/
</style>
