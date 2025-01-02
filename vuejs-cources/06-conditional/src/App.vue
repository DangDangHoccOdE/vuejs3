<script setup>
import { ref } from 'vue';

const isLoggIn = ref(false)

const toggleLoggIn = () => {
    isLoggIn.value = !isLoggIn.value
}

const isVisible = ref(false)

const toggleShow = () => {
  isVisible.value = !isVisible.value
}

const userStatus = ref('online')

const changeStatus=()=>{
  if(userStatus.value === 'online'){
    userStatus.value = 'away'
  }else if(userStatus.value === 'away'){
      userStatus.value = 'busy'
  }else if(userStatus.value === 'busy'){
      userStatus.value = 'online'
  }
}
</script>

<template>
  <div>
      <h1 v-if="isLoggIn">Chào mừng người dùng đã đăng nhập</h1>
      <h1 v-else>Chào mừng khách</h1>
      <button @click="toggleLoggIn">{{ isLoggIn ? "Dang xuat" : "Dang nhap" }}</button>
      <br/>
      <h1 v-if="userStatus==='online'">Người dùng đang online</h1>
      <h1 v-else-if="userStatus==='away'">Người dùng đang vắng mặt</h1>
      <h1 v-else-if="userStatus==='busy'">Người dùng đang bận</h1>
      <h1 v-else>Không rõ </h1>
      <button @click="changeStatus">Thay doi trang thai</button>
      <h1>{{ userStatus }}</h1>
      <br/>
      <h1 v-show="isVisible">Noi dung nay an hoac hien</h1>
      <button @click="toggleShow">{{ isVisible ? "An" : "Hien" }}</button>
    </div>

</template>

