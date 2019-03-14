<template>
  <div class="big">
    <div class="small one">
      <button class="btn_1" v-on:click="points += click_mod">Click</button>
    </div>

    <div class="small two">
        <p class="counter">{{points}}</p>
    </div>

    <div class="small thr">
      <div class="slaves">
        <tabs>
          <tab :active="true" class="shop one" title="Orjad">
            <div class="buy slave_1">
              <div class="info">
                <p class="title">Ori 1</p>
                <p class="desc">Ta annab 1 kulla :)</p>
              </div>
              <button class="buy_button" id="ori_1" v-on:click="shop_click('ori', '10', points, 1)">10g</button>
            </div>

            <div class="buy slave_2">
              <div class="info">
                <p class="title">Ori 2</p>
                <p class="desc">Ta annab 210 kulda :)</p>
              </div>
              <button class="buy_button" id="ori_2" v-on:click="shop_click('ori', '50', points, 10)">50g</button>
            </div>

            <div class="buy slave_3">
              <div class="info">
                <p class="title">Ori 3</p>
                <p class="desc">Ta annab 20 kulda :)</p>
              </div>
              <button class="buy_button" id="ori_3" v-on:click="shop_click('ori', '100', points, 20)">100g</button>
            </div>

            <div class="buy slave_4">
              <div class="info">
                <p class="title">PARIM ORI</p>
                <p class="desc">Ta teeb kõike :)</p>
              </div>
              <button class="buy_button" id="ori_4" v-on:click="shop_click('ori', '10000000', points, 10000)">10000000g</button>
            </div>
          </tab>
          <tab class="shop two" title="Riistad">
            <div class="buy tool_1">
              <div class="info">
                <p class="title">Riist 1</p>
                <p class="desc">Iga KLIKK annab +1 kulda :)</p>
              </div>
              <button class="buy_button" id="tool_1" v-on:click="shop_click('tool', '10', points, 1)">10g</button>
            </div>

            <div class="buy tool_2">
              <div class="info">
                <p class="title">Riist 2</p>
                <p class="desc">Iga KLIKK annab +5 kulda :)</p>
              </div>
              <button class="buy_button" id="tool_2" v-on:click="shop_click('tool', '100', points, 5)">100g</button>
            </div>

            <div class="buy tool_1">
              <div class="info">
                <p class="title">Riist 3</p>
                <p class="desc">Iga KLIKK annab +15 kulda :)</p>
              </div>
              <button class="buy_button" id="tool_3" v-on:click="shop_click('tool', '1000', points, 10)">1000g</button>
            </div>
          </tab>
        </tabs>
      </div>
    </div>
  </div>

</template>

<script>

  import Card from "../components/card";
  import Tabs from "../components/tabs";
  import Tab from "../components/tab";
  import Modal from "../components/modal";
  import Store_slot from "../components/store_slot";

  export default {
  components: {Modal, Tab, Tabs, Card},
    data() {
      return {
        click_mod: 1,
        points: 0,
        name: "",
        price: 0,
        inter_mon: 0,

      }
    },

    mounted() {
      setInterval((points, inter_mon) => {
        this.points += this.inter_mon;
      }, 100);
    },


    methods: {
      shop_click(name, price, money, mod) {
        if( money >= price){
        this.points -= price;

        if(name == "tool"){
          console.log("Ostsid riista " + price + " kulla eest");
          this.click_mod += mod;
        }
        else if(name == "ori"){
          console.log("Ostsid orja " +price+ " kulla eest");
          this.inter_mon += mod;
        }

        }
        else { alert("Ei saa osta");}
      },


    },
  }
</script>
<style>
.btn_1{width: 200px;height: 200px; border: 2px dashed orange; transition: ease .3s all; font-size: 30px;}
.btn_1:active{font-size: 20px;}
.btn_1:focus{outline: none;}
.buy_button:focus{outline: none;}
.buy_button:active{background-color: #ffbf}


.big{display:flex; flex-direction: row; margin-top: 80px; width: 100%; height:800px; justify-content: center;}
.small{border: 1px solid red; width: 25%;}
.small.one{display:flex; justify-content: center; align-items: center;}
.small.two{display:flex; justify-content: center; align-items: center;}
.small.two p{font-size: 30px;}
.shop{display:flex; justify-items: center; align-items: center; flex-direction: column;}

.buy{width: 100%; height: 100px; border-bottom: 2px solid red; background-color: #ffadad; display:flex; }
.buy:nth-child(1){border-top: 2px solid red;}
.title{margin-top: 5px;}
.info{margin-left:5px; width: 70%; height: 97px;}
.buy_button{width:30%; background-color: #ffd8d8; box-shadow: -10px 0px 10px -6px #dd7575;}
.buy_button:disabled{background-color: #7a2727;}

.tabs ul{border-bottom: 1px solid red;}
.tabs li.is-active a{border-bottom: 1px solid red;}
</style>
