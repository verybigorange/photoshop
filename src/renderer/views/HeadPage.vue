<template>
  <header class="head base_bgcolor">
      <div class="menu">
          <span class="iconfont icon-ps logo"></span>
          <menu-select  
            :class="index == active?'active':''" 
            v-for="(item,index) in menuList" 
            :menu="item" :key="item.title"
            @clicked="$store.commit('SETNEWACTIVE',index)"
          >
          </menu-select>
      </div>
  </header>
</template>

<script>
import MenuSelect from "components/MenuSelect"
import menu from "./data/menu"


export default {
  components:{
    MenuSelect
  },
  data(){
    return {
      menuList:menu,
    }
  },
  computed:{
    active(){
      return this.$store.state.active
    }
  }
}
</script>

<style lang="scss" scoped>
.head{
  background: #535353;
  padding:0 10px;
}

.menu{
  height: 34px;
  line-height: 30px;
  white-space: nowrap;
  .logo{
    font-size: 20px;
    color: #7fa9d2;
    margin-right: 20px;
  }
}
</style>
