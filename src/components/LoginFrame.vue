<template>
  <div class="log-frame">
    <img src="img/logo_l@svg.svg" alt="title">
    <h3>享受美食好味道</h3>
    <div class="login-window">
        <h3>{{msg}}</h3>
        <label for="email">Email Adderss*</label><br>
        <input type="text" name="email" class="email" placeholder="請輸入你的信箱">
        <router-link to="/register" class="hint">尚未註冊？</router-link>
        <br>
        <label for="password">Password*</label><br>
        <input type="password" name="password" class="password">
        <router-link to="/password" class="hint">忘記密碼？</router-link>
        <div class="btn-item">
            <button type="button" class="btn btn-cancel">取消</button>
            <button type="button" class="btn btn-enter">送出</button>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Log In'
    }
  }
}
</script>
