<template>
  <div class="container" style="width: 600px;">
    <div class="alert alert-danger alert-dismissable" v-if="error" role="alert">
      {{errorMsg}}
    </div>
    <div class="alert alert-success"  v-if="success" role="alert">{{errorMsg}}</div>
    <div class="compareNumber" style="flex-direction: column;">
      <div >
        <label> 账号：</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="account" name="text" id="account" placeholder= "请输入账号" />
      </div>
      <div>
        <label >  密码：</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="pwd" name="text" id="pwd" placeholder="请输入密码" />
      </div>
      <div>
        <label >手机号:</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="iphone" name="text" id="iphone" placeholder="请输入手机号码" />
      </div>
      <div>
        <label >验证码:</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="recode" name="text" id="recode" placeholder="请输入验证码" />
        <a class="btn btn-success" style="margin-left: 10px;" @click="">点击发送验证码</a>
      </div>
    </div>
    <div class="compareNumber"  style="padding: 0px 120px;margin-top: 10px;">
      <a class="btn btn-info btn-lg btn-block" @click="regist()">注册</a>
    </div>
  </div>
</template>

<script>

export default {
  name: 'regist',
  data () {
    return {
      msg: 'registTemplate',
      account: '',
      pwd: '',
      iphone: '',
      recode: '',
      error: false,
      errorMsg: '',
      success: false
    }
  },
  methods: {
    regist () {
      var account = this.account
      var pwd = this.pwd
      var iphone = this.iphone
      var recode = this.recode
      if (account != undefined && pwd != undefined
       &&  iphone != undefined && recode != undefined
       && account != '' && pwd != ''
       &&  iphone != '' && recode != '') {
        this.error = false
        this.success = true
        this.errorMsg = '注册成功！'
      } else if (account == undefined || account == '') {
        this.success = false
        this.error = true
        this.errorMsg = '用户名不能为空！'
      } else if (pwd == undefined || pwd == '') {
        this.success = false
        this.error = true
        this.errorMsg = '密码不能为空！'
      } else if (iphone == undefined || iphone == ''){
        this.success = false
        this.error = true
        this.errorMsg = '手机号码不能为空！'
      } else if (recode == undefined || recode == ''){
        this.success = false
        this.error = true
        this.errorMsg = '验证码不能为空！'
      }
      return ''
    }
  },
  beforeCreate () {
    console.log(this.$route)
    var co = this.$route.query.choice
    console.log(co)
    this.$root.$data.choice = co
  }
}
</script>

<style>
</style>
