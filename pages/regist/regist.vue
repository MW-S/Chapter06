<template>
  <div class="main"  id="login">
    <div class="row" align="center">
       <transition enter-active-class="animated bounceInDown"
                    :duration="{ enter: 1000}">
          <component :is="compontentName"></component>
       </transition>
    </div>
  </div>
</template>

<script>
import RegistCom from '../../components/RegistCom.vue'


export default {
  map: 'regist',
  components: {
    RegistCom: RegistCom
  },
  data () {
    return {
      compontentName: 'RegistCom',
      cur: 0,
      choice: 'first',
    }
  }
}
</script>

<style>
  .main {
    height: 500px;
    background-color: #f8f8f8;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .main div p {
    font-size: 30px;
  }
  .compareNumber {
  	padding: 0px;
  	display: flex;
  	flex-direction: row;
  	justify-content: space-around;
  }

  .compareNumber div {
  	display: flex;
  	flex-direction: row;
  	margin: 10px 20px;
  }

  .compareNumber label {
  	display: flex;
  	align-items: center;
  	font-size: 20px;
  }
</style>
