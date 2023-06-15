<template id="shop">
    <div v-bind:style="background">
        <p class="main-text">闰土的瓜摊</p>
        <p class="huojia-text">点击西瓜获取售价</p><br>
        <div class="guatanhuojia">
            <ul style="padding-left: 5px;padding-right: 5px;">
                <li class="gualiebiao">
                    <div>
                    <button class="gua" v-on:click="howmoney1"><img width="150px" src="../picture/gua.png" >
                    <br>瓜多少钱一斤</button>
                    </div>
                </li>
                <li class="gualiebiao">
                    <div>
                    <button class="gua" v-on:click="howmoney2"><img width="150px" src="../picture/gua.png" >
                    <br>瓜多少钱一斤</button>
                    </div>
                </li>
                <li class="gualiebiao">
                    <div>
                    <button class="gua" v-on:click="howmoney3"><img width="150px" src="../picture/shenggua.png" >
                    <br>瓜多少钱一斤</button>
                    </div>
                </li>
                <li class="gualiebiao">
                    <div>
                    <button class="gua" v-on:click="howmoney3"><img width="150px" src="../picture/cha.png" >
                    <br>猹多少钱一斤</button>
                    </div>
                </li>

            </ul>
        </div>
        <button class="tiaogua" v-on:click="tiaogua">挑一个</button>
        <div class="zhaocha" >
            <ul style="display: inline-table;margin: 5px 0 5px 0;padding-right: 5px;width: 100%;padding-left: 5px;padding-right: 5px; ">
                <li  class="cha-list">
                    <div>
                    <button class="cha" v-on:click="cha1">
                    {{ msg11 }}<br>{{ msg12 }}</button>
                    </div>
                </li>
                <li class="cha-list">
                    <div>
                    <button class="cha" v-on:click="cha2">
                    {{ msg21 }}<br>{{ msg22 }}</button>
                    </div>
                </li>
                <li class="cha-list">
                    <div>
                    <button class="cha" v-on:click="cha3">
                    {{ msg31 }}<br>{{ msg32 }}</button>
                    </div>
                </li>
                <li class="cha-list">
                    <div>
                    <button class="cha" v-on:click="cha4">
                    {{ msg41 }}<br>{{ msg42 }}</button>
                    </div>
                </li>
                
            </ul>
            
        </div>
        
        <p class="main-text">{{ msg }}</p>
    </div>

</template>

<style>

button{
    background-color: aliceblue;
}
#shop{
    display: flex;
    text-align: center;
    width: 100%;
    height: 100%;
    color: brown;
}
.text{
    color: brown;
    font-size: 30px;
}


.main-text{
    color: brown;
    font-size: 40px;
    font-weight: bold;
    background-color: aliceblue;
    margin: 0px;

}

.huojia-text{
    width: 100%;
    color: brown;
    font-size: 30px;
    height: 30px;
    margin: 0px;
}
.gua{
    font-size: 20px;
    color: #123201;
    padding: 5px;
    background-color: aliceblue;
}
.guatanhuojia{
    height: 100%;
}
.gualiebiao{
    display: inline-table;
    width: 150px;
    height: 180px;
    padding: 5px;
}
.zhaocha{
    margin: 5px 0 5px 0;
    width: 100%;
}
.cha-list{
    display: inline-block;
    width: 140px;
    padding: 5px;
}
.cha{
    height: 50px;
    width: 140px;
}
</style>

<script>
  export default {
  name: 'ShopView',
  data(){
    return{
        shu:0,
        cheng:0,
        gua:0,
        laoban:1,
        msg:'有一个人前来买瓜',
        money:0,
        gua1:2,
        gua2:5,
        weight:15,
        guaNow:0,
        msg11:'你这瓜皮子金子做的',
        msg12:'还是瓜粒子金子做的',
        msg21:'你这瓜',
        msg22:'保熟吗？',
        msg31:'那他要是不熟',
        msg32:'怎么办啊？',
        msg41:'这哪够15斤',
        msg42:'你这称有问题啊',
        background:'background-color:white;'
    } 
  },
  methods:{
    howmoney1(){
        if(this.laoban==1){
        this.msg=this.gua1+'块钱一斤',
        this.guaNow=this.gua1,
        this.shu=0
        }
    },
    howmoney3(){
        this.msg='你故意找茬是吧？'
    },
    howmoney2(){
        if(this.laoban==1){
        this.msg=this.gua2+'块钱一斤',
        this.guaNow=this.gua2,
        this.shu=0
        }
    },
    tiaogua(){
        if(this.laoban==1){
        if (this.guaNow==0)
        {  this.msg='你还没选择瓜的品种呐！'}
        else
        {   this.money=this.guaNow*this.weight,
            this.msg=this.weight+'斤,'+this.money+'块'}
        }
        
    },
    cha1(){
        if(this.laoban==1){
        if (this.guaNow!=0){this.msg="你看这现在哪有瓜呀，这都是大鹏的瓜"}
        else{this.msg="? ? ? ? ? ? ? ?"}
        }
        
        
    },
    cha2(){
        if(this.laoban==1){
        if(this.guaNow>0){
        if(this.shu<1)
        {this.msg='我一开水果摊的，能卖给你生瓜蛋子啊？'}
        else {
            if(this.guaNow>0)
            {this.msg='你故意找茬是吧？你要不要吧！'}
        }
        }
        else{this.msg="? ? ? ? ? ? ? ?"}
        }
        this.shu++
    },
    cha3(){
        if(this.laoban==1){
            if(this.gua==0)
        {
        if (this.guaNow!=0){
            this.msg="他要是不熟，我自己吃了它，满意了吧？",
            this.gua=1,
            this.msg31='你说的他要是不熟',
            this.msg32=' 你就自己吞了啊'
        }
        else{this.msg="? ? ? ? ? ? ? ?"}
        }
        else
            if(this.cheng>0){this.msg='你TM的劈我瓜是吧？！'}
        }
        
        },
    
    cha4(){
        if(this.laoban==1){
        if (this.guaNow>0&&this.money>0){
        if (this.cheng==0)
        {
            this.msg='你TM故意找茬是吧？你要不要吧！要不要！？',
            this.msg41=' 拿起西瓜刀',
            this.msg42='公鸡瓜摊老板',
            this.cheng++
        }
        else{
            this.msg='杀人啦，杀人啦',
            this.background='background-color:green',
            this.msg11=this.msg12=this.msg31=this.msg32=this.msg21=this.msg22=this.msg41=this.msg42='杀人啦！',
            this.laoban=0
        }
        }else{this.msg='? ? ? ? ? ? ? ?'}
        
        }
        
    }, 

  }
  
}
</script>