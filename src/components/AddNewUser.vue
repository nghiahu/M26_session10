<template>
  <!-- Form thêm mới nhân viên -->
  <div class="overlay" h>
      <form class="form" @submit.prevent="handleSubmit">
        <div class="d-flex justify-content-between align-items-center">
          <h4>Chỉnh sửa nhân viên</h4>
          <i class="fa-solid fa-xmark" @click="closeShowFrom"></i>
        </div>
        <div>
          <label class="form-label" for="userName">Họ và tên</label>
          <input v-model="employee.name" id="userName" type="text" class="form-control" />
          <!-- <div class="form-text error">Họ và tên không được để trống.</div> -->
        </div>
        <div>
          <label class="form-label" for="dateOfBirth">Ngày sinh</label>
          <input v-model="employee.dateOfBirth" id="dateOfBirth" type="date" class="form-control" />
        </div>
        <!-- <div class="form-text error">
          Ngày sinh không được lớn hơn ngày hiện tại.
        </div> -->
        <div>
          <label class="form-label" for="email">Email</label>
          <input v-model="employee.email" id="email" type="email" class="form-control" />
        </div>
        <!-- <div class="form-text error">Email không được để trống.</div> -->
        <div>
          <label class="form-label" for="address">Địa chỉ</label>
          <textarea v-model="employee.address" class="form-control" id="address" rows="3"></textarea>
        </div>
        <div>
          <button class="w-100 btn btn-primary">Thêm mới</button>
        </div>
      </form>
    </div>
</template>

<script setup>
import { reactive } from 'vue';

    const emit = defineEmits(["closeFrom"])
    function closeShowFrom(){
        emit("closeFrom")
    };

    const employee = reactive({
        id: Math.floor(Math.random() * 100000000000),
        name: "",
        dateOfBirth: "",
        email: "",
        address: "",
        status: true
    })
    function handleSubmit(){
        
    }
</script>

<style>

</style>