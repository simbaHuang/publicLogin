<template>
  <div class="login">
    <Form :model="formModel">
      <FormItem>
        <span class="form-tit" :class="titType.phone">手机号</span>
        <Input class="form-ipt" v-model="formModel.phone" @on-focus="onInputFocus('phone')" @on-blur="onInputBlur('phone')"></Input>
      </FormItem>
      <FormItem>
        <span class="form-tit" :class="titType.code">验证码</span>
        <Input class="form-ipt" v-model="formModel.code" :style="{ width: '50%' }" @on-focus="onInputFocus('code')" @on-blur="onInputBlur('code')"></Input>
        <Button class="" :style="{ width: '45%', marginLeft: '3%' }">获取验证码</Button>
      </FormItem>

      <FormItem>
        <Button :style="{ width: '100%' }" type="primary" @click="submit()">提交</Button>
      </FormItem>
    </Form>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      formModel: {},
      titType: {}
    }
  },
  methods: {
    onInputFocus (type) {
      this.titType[type] = { focus: true }
    },
    onInputBlur (type) {
      this.titType[type] = this.formModel[type] ? { focus: true } : { focus: false }
    },
    submit () {
      this.$router.push({ path:'/register' });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .form-tit{
    position: absolute;
    top: 0;
    height: 32px;
    padding-left: 7px;
    color: #888;
    font-size: 14px;
    transition: all .2s ease-in-out;
  }
  .form-tit.focus{
    top: -24px;
    font-size: 12px;
  }
  .ivu-input{
    background-color: transparent;
    color: #333;
    border: none;
    border-bottom: 1px solid #dcdee2;
  }
  .ivu-input:focus,
  .ivu-btn:focus{
    box-shadow: none;
  }
</style>
