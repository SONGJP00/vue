<template>

  <div class="black-bg" v-if="moderoften1 == 1">
    <div class="white-bg">
      <h4>詳しく</h4>
      <p>{{coment[0]}}</p>
      <button v-on:click="moderoften1 = 0">出る</button> 
    </div>
  </div>
  <div class="black-bg" v-if="moderoften2 == 1">
    <div class="white-bg">
      <h4>詳しく</h4>
      <p>{{coment[1]}}</p>
      <button v-on:click="moderoften2 = 0">出る</button> 
    </div>
  </div>
  <div class="black-bg" v-if="moderoften3 == 1">
    <div class="white-bg">
      <h4>詳しく</h4>
      <p>{{coment[2]}}</p>
      <button v-on:click="moderoften3 = 0">出る</button> 
    </div>
  </div>

  <div class="menu">
    <a v-for = "(m,i) in Menu" :key="i">{{m}}</a>
  </div>

  
  <div>
    <img src=".\assets\미니쿠페.jpg" class="room-img"> 
    <h4 @click="moderoften1 = 1">{{ products[0] }}</h4>
    <p>{{price1}}万円</p>
    <button v-on:click="お聞き合わせ1[0]++">お聞き合わせ</button> 
    <span>お聞き合わせ数 : {{お聞き合わせ1[0]}}</span>
  </div>

  <div>
    <img src=".\assets\아이오닉5.jpg" class="room-img">
    <h4 @click="moderoften2 = 1">{{ products[1] }}</h4>
    <p>{{price2}}万円</p>
    <button v-on:click="お聞き合わせ1[1]++">お聞き合わせ</button>
    <span>お聞き合わせ数 : {{お聞き合わせ1[1]}}</span>
  </div>

  <div>
    <img src=".\assets\제네시스g80.jpg" class="room-img">
    <h4 @click="moderoften3 = 1">{{ products[1] }}</h4>
    <p>{{price3}}万円</p>
    <button v-on:click="お聞き合わせ1[2]++">お聞き合わせ</button>
    <span>お聞き合わせ数 : {{お聞き合わせ1[2]}}</span>
  </div>
  
</template>

<script>


import data from "./assets/car.js";

export default {
  name: 'App', 
  data(){
    return {
      coment:[`コンパクトだけど強い`,`電気自動車の安定感`,`社長の雰囲気を味わえる`],
      cars : data,
      moderoften1 : 0,
      moderoften2 : 0,
      moderoften3 : 0,
      お聞き合わせ1 : [0,0,0],
      Menu : [`Home`,`Shop`,`QnA`],
      price1 : 1000,
      price2 : 2000,
      price3 : 3000,
      products : [`ミニークぺ`,`アイオニック５`,`ズェネシスG80`],
    }
  },
  //methods: {
    //increase(){
      //this.お聞き合わせ1++;
    //}
  //},
  components: {
    
  }
}
</script>

<style>

body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}


.room-img {
  height: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslategray;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
