<template>
  <div class="login">
    <Form :model="formModel">
        <Upload action
          accept='image'
          @on-success="uploadAvatar()">
          <Avatar icon="ios-person" size="large" :src="formModel.avatar"/>
        </Upload>
      </FormItem>
      <FormItem>
        <span class="form-tit" :class="titType.account">账号</span>
        <Input class="form-ipt" v-model="formModel.account" @on-focus="onInputFocus('account')" @on-blur="onInputBlur('account')"></Input>
      </FormItem>
      <FormItem>
        <span class="form-tit" :class="titType.password">密码</span>
        <Input class="form-ipt" type="password" v-model="formModel.password" @on-focus="onInputFocus('password')" @on-blur="onInputBlur('password')"></Input>
      </FormItem>

      <FormItem>
        <Button :style="{ width: '100%' }" type="primary">提交</Button>
      </FormItem>
    </Form>
  </div>
</template>

<script>
export default {
  name: 'Register',
  data () {
    return {
      formModel: {},
      titType: {},
    }
  },
  methods: {
    onInputFocus (type) {
      this.titType[type] = { focus: true }
    },
    onInputBlur (type) {
      this.titType[type] = this.formModel[type] ? { focus: true } : { focus: false }
    },
    uploadAvatar (response, file, fileList) {

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
