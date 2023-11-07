<template>
  <div class="log-frame">
    <img src="img/logo_l@svg.svg" alt="title">
    <h3>享受美食好味道</h3>
    <div class="register-window">
        <h3>REGISTER</h3>
        <div class="register">
            <div class="input">
                <label for="email">Email Adderss*</label><br>
                <input type="text" name="email" class="email" placeholder="請輸入你的信箱">
                <br>
                <label for="password">Password*</label><br>
                <input type="password" class="password" name="password" value="">
                <br>
                <router-link to="/login" class="hint">已經有帳號了？</router-link>
                <div class="btn-item">
                    <button type="button" class="btn btn-enter">註冊</button>
                </div>
            </div>
        </div>
    </div>
    </div>
</template>
