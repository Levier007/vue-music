<template>
  <li class="item">
    <div class="bgImg">
      <img
        :src="item.picUrl || item.coverImgUrl + '?param=200y200'"
        :alt="item.name"
        style="width: 100px; height: 100px"
      />
      <div class="count">
        <i class="iconfont icon-bofangqi-bofang"></i>
        <span>{{ utils.tranNumber(item.playCount, 0) }}</span>
      </div>
    </div>
    <div class="info">
      <h5>{{ item.name }}</h5>
    </div>
  </li>
</template>

<script>
export default {
  name: "SongSheet",
  props: ["item"],
};
</script>

<style scoped>
.item {
  float: left;
  width: 100px;
  height: 150px;
  margin: 0 25px 25px 25px;
  cursor: pointer;
  list-style: none;
}
.info {
  margin-top: 10px;
}
h5 {
  font-size: 14px;
  /* 多行文字超出最后一行省略号 */
  word-break: break-all;
  text-overflow: ellipsis;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
.bgImg {
  position: relative;
}
.bgImg img {
  border-radius: 2px;
}
.bgImg::before{
  z-index: -1;
  content: '';
  position: absolute;
  width: 90px;
  height: 90px;
  right: -5px;
  top: 5px;
  background-color: rgba(0,0,0,0.2);
  border-radius: 2px;
  opacity: 0.9;
}
.bgImg::after{
  z-index: -2;
  content: '';
  position: absolute;
  width: 80px;
  height: 80px;
  right: -10px;
  top: 10px;
  background-color: rgba(0,0,0,0.2);
  border-radius: 2px;
  opacity: 0.8;
}
.count {
  position: absolute;
  right: 10px;
  top: 10px;
  color: white;
  padding: 1px;
  background-color: black;
}
</style>