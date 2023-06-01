<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

import IconHide from '@/views/icons/IconHide.vue'
import IconLock from '@/views/icons/IconLock.vue'

const router = useRouter()
const show = ref(false)

const login = function () {
  router.push({ name: 'account' })
}
</script>

<template>
  <main>
    <div class="col-container">
      <div class="col-container">
        <h1>Enter your password</h1>
        <div class="row-container">
          <div>
            <img src="../assets/images/avatar.png" alt="Sarah Bills" width="64" height="64" />
          </div>
          <div>
            <p>Business Account</p>
            <h2>Sarah Bills</h2>
          </div>
        </div>
        <div>
          <p>Password</p>
          <div class="row-container">
            <div class="icon lock"><IconLock /></div>
            <input :type="show ? 'text' : 'password'" />
            <div class="icon action-icon" @click="show = !show"><IconHide /></div>
          </div>
        </div>
        <div class="row-container login">
          <div class="row-container">
            <label class="switch">
              <input type="checkbox" checked />
              <span class="slider round"></span>
            </label>
            <p>Stay signed in</p>
          </div>
          <button @click="login">Continue</button>
        </div>
      </div>
      <router-link :to="{ name: 'reset' }">Reset password</router-link>
    </div>
  </main>
</template>

<style scoped>
main {
  width: 484px;
  height: 477px;
  background-color: #fff;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 16px;
  padding: 75px;
  box-shadow: 0 44px 104px rgba(19, 43, 80, 0.1);
}

h1 {
  font-size: 24px;
}

.col-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  gap: 20px;
}

.row-container {
  display: flex;
  align-items: center;
  gap: 10px;
  position: relative;
}

h2 {
  font-size: 16px;
}

p {
  font-size: 13px;
}

input {
  margin-block: 10px;
  line-height: 2.5;
  padding: 5px 10px 5px 35px;
  border-radius: 8px;
  width: 100%;
  flex: 1;
  border: 1px solid #132b50;
}

.icon {
  display: flex;
  justify-content: center;
  align-items: center;
}

.action-icon {
  cursor: pointer;
}

.lock {
  position: absolute;
  left: 10px;
}

.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 28px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transition: 0.4s;
  border: 1px solid #132b50;
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

.slider:before {
  position: absolute;
  content: '';
  height: 20px;
  width: 20px;
  left: 3px;
  bottom: 3px;
  background-color: #132b50;
  transition: 0.4s;
}

input:checked + .slider:before {
  transform: translateX(21px);
}

.login {
  justify-content: space-between;
  margin-right: 40px;
}

.login p {
  font-size: 13px;
}

button {
  background-color: #132b50;
  border-radius: 8px;
  color: #fff;
  padding: 12px 14px;
  cursor: pointer;
}

a {
  color: #132b50;
  font-size: 13px;
}
</style>
