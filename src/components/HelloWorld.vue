<template>
  <div class="hello">
      全选 <p class="p" :class="{red:list.length == itemObjList.length}" @click="all"></p>
     <div v-for="(item,i) in itemObjList" :key="i">
       {{item.name}} 
          <p :class="{p:true,red:list.includes(item.index)}" @click="fn(item.index)"></p>
     </div>



    

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: null,
      one:false,
      // 选中的按钮集合
      list:[],
      // 数据列表
      itemObjList:[
        {name:"saf",index:1},
        {name:"sdfa",index:2},
        {name:"sf",index:3},
        {name:"讽德诵功",index:4},
        {name:"割发代首",index:5},
        {name:"问题",index:6},
        {name:"是大法官",index:7},
        {name:"士",index:8},
        {name:"分公司",index:9},
        {name:"委托人",index:10},
        {name:"羊肉汤",index:11},
        {name:"特意",index:12},
      ]
    }
  },
  methods:{
    fn(item){
      console.log(this.list.includes(item))
      if(this.list.includes(item)){
        this.list = this.list.filter((obj)=>{
            return obj != item
        })
      }else{
        this.list.push(item)
      }
    },
    all(){
      console.log(111)
      if(this.list.length == this.itemObjList.length){
        this.list = []
      }else{
        this.list = []
        this.itemObjList.forEach(element => {
          this.list.push(element.index)
        });
      }
    }
  }
}
</script>
<style scoped>
  .red{
    background-color: red;
  }
  .p{
    width: 30px;
    height: 30px;
    /* background-color: aliceblue; */
    border:1px solid red;
    border-radius: 50%;
    /* display: inline-block; */
  }
</style>
