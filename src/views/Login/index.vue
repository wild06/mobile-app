<template>
  <div>
    <van-nav-bar
      title="用户登录"
      left-arrow
      @click-left="$router.go(-1)"
    />
    <div>
      <p class="title">欢迎回来</p>
      <form class="form">
        <input type="email" class="input" placeholder="Email" v-model="email">
        <input type="password" class="input" placeholder="Password" v-model="password">
        <p class="page-link">
          <span class="page-link-label">Forgot Password?</span>
        </p>
        <button class="form-btn" @click="submit">登录</button>
      </form>
      <p class="sign-up-label">
        还没有账号？<span class="sign-up-link">注册</span>
      </p>
    </div>
  </div>
</template>

<script >
import { Toast } from 'vant'
export default {
  name: 'LoginIndex',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    submit () {
      if (this.email === '' || this.password === '') {
        console.log('用户和密码不为空')
      } else {
        if (this.email === '13134829583@163.com' && this.password === '123456') {
          Toast.loading({
            message: '登录中',
            forbidClick: true,
            duration: 500
          })
          setTimeout(() => {
            this.$router.push('/home')
          }, 1000)
        }
      }
    }
  }
}
</script>

<style lang="less" scoped>

.title {
  text-align: center;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  margin: 10px 0 30px 0;
  font-size: 28px;
  font-weight: 800;
}

.form {
  width: 90%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 18px;
  margin-bottom: 15px;
}

.input {
  border-radius: 20px;
  border: 1px solid #c0c0c0;
  outline: 0 !important;
  box-sizing: border-box;
  padding: 12px 15px;
}

.page-link {
  text-decoration: underline;
  margin: 0;
  text-align: end;
  color: #747474;
  text-decoration-color: #747474;
}

.page-link-label {
  cursor: pointer;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  font-size: 9px;
  font-weight: 700;
}

.page-link-label:hover {
  color: #000;
}

.form-btn {
  padding: 10px 15px;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  border-radius: 20px;
  border: 0 !important;
  outline: 0 !important;
  background: teal;
  color: white;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

.form-btn:active {
  box-shadow: none;
}

.sign-up-label {
  margin: 0;
  font-size: 10px;
  color: #747474;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}

.sign-up-link {
  margin-left: 1px;
  font-size: 11px;
  text-decoration: underline;
  text-decoration-color: teal;
  color: teal;
  cursor: pointer;
  font-weight: 800;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}

.buttons-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  margin-top: 20px;
  gap: 15px;
}

.apple-login-button,
.google-login-button {
  border-radius: 20px;
  box-sizing: border-box;
  padding: 10px 15px;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 10px 36px 0px,
  rgba(0, 0, 0, 0.06) 0px 0px 0px 1px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
  "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
  font-size: 11px;
  gap: 5px;
}

.apple-login-button {
  background-color: #000;
  color: #fff;
  border: 2px solid #000;
}

.google-login-button {
  border: 2px solid #747474;
}

.apple-icon,
.google-icon {
  font-size: 18px;
  margin-bottom: 1px;
}
</style>
