<template>
  <div id="login">
    <h1>欢迎登陆长时科技</h1>
    <div class="top-hat"></div>
    <div class="longin-box">
      <!-- logo -->
      <div class="login-wrap">
        <div class="login-box"></div>
      </div>
      <!-- 登陆的表达 -->
      <div class="input-grop" :class="{ active: act_index === 1 }">
        <label for="cm_code">公司编号：</label>
        <input
          @focus="act_index = 1"
          type="number"
          id="cm_code"
          v-model="cm_code"
        />
      </div>
      <div class="input-grop" :class="{ active: act_index === 2 }">
        <label for="cm_code">员工编号：</label>
        <input
          @focus="act_index = 2"
          type="number"
          id="PNO"
          v-model="PNO"
        />
      </div>
      <div class="input-grop" :class="{ active: act_index === 3 }">
        <label for="cm_code">用户密码：</label>
        <input
          @focus="act_index = 3"
          type="password"
          id="Passw"
          v-model="passwd"
        />
      </div>
      <div class="ck-row">
        <div class="ckbox_wrap">
          <i class="iconfont icon-Multipleselection-unchecked"></i>
          <span>记住密码</span>
        </div>
        <div class="ckbox_wrap ckbox_wrap_one">
          <i class="iconfont icon-Multipleselection-unchecked"></i>
          <span>自动登录</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import '../assets/IconLibrary/iconfont.css'
export default {
  data() {
    return {
      act_index: 1,
      cm_code: "",
      PNO:"",
      passwd:""
    };
  }
};
</script>

<style lang="scss" scoped>
#login {
  width: 100%;
  height: 100%;
  background-color: #2ade69;
  h1 {
    text-align: center;
    font-size: px2rem(36);
    height: px2rem(36);
    padding: px2rem(148-36-44) 0 px2rem(44) 0;
    line-height: px2rem(36);
    color: #fff;
  }
  .top-hat {
    width: px2rem(537);
    height: px2rem(18);
    background-color: #eee;
    margin: 0 auto;
    border-radius: px2rem(18) px2rem(18) 0 0;
  }
  .longin-box {
    width: px2rem(680);
    height: px2rem(836);
    margin: 0 auto;
    border-radius: px2rem(20);
    background-color: #fff;
    .login-wrap {
      padding: px2rem(80) 0;
      .login-box {
        width: px2rem(190);
        height: px2rem(190);
        margin: 0 auto;
        background: url(../assets/logo.png);
        background-size: cover;
      }
    }
    @mixin rowStyle(){
      padding: 0 px2rem(36);
      color: $text-color;
      width: px2rem(401);
      margin: 0 auto px2rem(30);
    }
    .input-grop {
      border: px2rem(2) solid #e2e2e2;
      border-radius: px2rem(45);
      font-size: $text-size-mid;
      line-height: px2rem(90);
      @include rowStyle();
      input {
        border: none;
        width: px2rem(200);
        font-size: $text-size-mid;
        line-height: px3rem(90);
        padding-left: 1em;
      }
      input:focus {
        border: none;
        outline: none;
      }
    }
    .input-grop.active {
      color: $act-color;
      border: px2rem(2) solid $act-color;
    }
    .ck-row{
      @include rowStyle();
      font-size: $text-size;
      display: flex;
      flex-direction: row;
      .ckbox_wrap{
        padding-top: px2rem(8);
        display: flex;
        flex-direction: row;
        align-items: center;
        i::before{
          display: inline-block;
          height: px2rem(32);
          width: px2rem(32);
          font-size: px2rem(32);
        }
        span{
          padding-left: px2rem(5);
        }
      }
      .ckbox_wrap_one{
        padding-left: px2rem(36);
      }
    }
  }
}
</style>
