<script setup>
  import { ref } from "vue";
import AddNewUserVue from "./components/AddNewUser.vue";
  const isShowFrom = ref(false)
  function hadleShowFrom(){
    isShowFrom.value = true
  }
  function handleClose(){
    isShowFrom.value = false
  }
</script>

<template>
  <body>
    <div class="w-[80%] m-auto mt-4 h-[100vh]">
      <main class="main">
        <header class="d-flex justify-content-between mb-3">
          <h3>Nhân viên</h3>
          <button class="btn btn-primary" @click="hadleShowFrom">Thêm mới nhân viên</button>
        </header>
        <div class="d-flex align-items-center justify-content-end gap-2 mb-3">
          <input
            style="width: 350px"
            type="text"
            class="form-control"
            placeholder="Tìm kiếm theo email"
          />
          <i class="fa-solid fa-arrows-rotate" title="Refresh"></i>
        </div>
        <!-- Danh sách nhân viên -->
        <table class="table table-bordered table-hover table-striped">
          <thead>
            <tr>
              <th>STT</th>
              <th>Họ và tên</th>
              <th>Ngày sinh</th>
              <th>Email</th>
              <th>Địa chỉ</th>
              <th>Trạng thái</th>
              <th colspan="2">Chức năng</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>1</td>
              <td>Nguyễn Văn A</td>
              <td>28/02/1990</td>
              <td>nvana@gmail.com</td>
              <td>Ba Đình, Hà Nội</td>
              <td>
                <div style="display: flex; align-items: center; gap: 8px">
                  <div class="status status-active"></div>
                  <span> Đang hoạt động</span>
                </div>
              </td>
              <td>
                <span class="button button-block">Chặn</span>
              </td>
              <td>
                <span class="button button-edit">Sửa</span>
              </td>
              <td><span class="button button-delete">Xóa</span></td>
            </tr>
            <tr>
              <td>2</td>
              <td>Trần Thị B</td>
              <td>15/07/1985</td>
              <td>ttb@gmail.com</td>
              <td>Cầu Giấy, Hà Nội</td>
              <td>
                <div style="display: flex; align-items: center; gap: 8px">
                  <div class="status status-stop"></div>
                  <span> Ngừng hoạt động</span>
                </div>
              </td>
              <td>
                <span class="button button-block">Bỏ chặn</span>
              </td>
              <td>
                <span class="button button-edit">Sửa</span>
              </td>
              <td><span class="button button-delete">Xóa</span></td>
            </tr>
            <tr>
              <td>3</td>
              <td>Lê Văn C</td>
              <td>03/10/2000</td>
              <td>lvc@gmail.com</td>
              <td>Hai Bà Trưng, Hà Nội</td>
              <td>
                <div style="display: flex; align-items: center; gap: 8px">
                  <div class="status status-stop"></div>
                  <span> Ngừng hoạt động</span>
                </div>
              </td>
              <td>
                <span class="button button-block">Bỏ chặn</span>
              </td>
              <td>
                <span class="button button-edit">Sửa</span>
              </td>
              <td><span class="button button-delete">Xóa</span></td>
            </tr>
            <tr>
              <td>4</td>
              <td>Phạm Thị D</td>
              <td>20/05/1995</td>
              <td>ptd@gmail.com</td>
              <td>Hoàn Kiếm, Hà Nội</td>
              <td>
                <div style="display: flex; align-items: center; gap: 8px">
                  <div class="status status-active"></div>
                  <span> Đang hoạt động</span>
                </div>
              </td>
              <td>
                <span class="button button-block">Chặn</span>
              </td>
              <td>
                <span class="button button-edit">Sửa</span>
              </td>
              <td><span class="button button-delete">Xóa</span></td>
            </tr>
            <tr>
              <td>5</td>
              <td>Ngô Văn E</td>
              <td>12/11/1988</td>
              <td>nve@gmail.com</td>
              <td>Cầu Giấy, Hà Nội</td>
              <td>
                <div style="display: flex; align-items: center; gap: 8px">
                  <div class="status status-active"></div>
                  <span> Đang hoạt động</span>
                </div>
              </td>
              <td>
                <span class="button button-block">Chặn</span>
              </td>
              <td>
                <span class="button button-edit">Sửa</span>
              </td>
              <td><span class="button button-delete">Xóa</span></td>
            </tr>
          </tbody>
        </table>
        <footer class="d-flex justify-content-end align-items-center gap-3">
          <select class="form-select">
            <option selected>Hiển thị 10 bản ghi trên trang</option>
            <option>Hiển thị 20 bản ghi trên trang</option>
            <option>Hiển thị 50 bản ghi trên trang</option>
            <option>Hiển thị 100 bản ghi trên trang</option>
          </select>
          <ul class="pagination">
            <li class="page-item">
              <a class="page-link" href="#">Previous</a>
            </li>
            <li class="page-item"><a class="page-link" href="#">1</a></li>
            <li class="page-item"><a class="page-link" href="#">2</a></li>
            <li class="page-item"><a class="page-link" href="#">3</a></li>
            <li class="page-item"><a class="page-link" href="#">Next</a></li>
          </ul>
        </footer>
      </main>
    </div>
    <AddNewUserVue v-if="isShowFrom" @closeFrom="handleClose"/>
  </body>
</template>

<style>
  * {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-size: 14px;
  font-family: sans-serif;
}

.main {
  /* height: 100vh; */
  margin: 50px 100px;
}

.fa-arrows-rotate {
  font-size: 20px;
  cursor: pointer;
  color: gray;
}

.fa-arrows-rotate:hover {
  color: rgb(184, 180, 180);
  transform: rotate(20deg);
  transition: all 0.5s linear;
}

.button {
  padding: 4px 12px;
  line-height: 30px;
  border-radius: 4px;
  color: #fff;
  cursor: pointer;
}

.button-edit {
  background-color: orange;
}

.button-delete {
  background-color: red;
}

.button-block {
  background-color: green;
}

td:first-child,
td:nth-child(6),
td:nth-child(7) {
  text-align: center;
}

.form-select {
  width: 270px !important;
}

.overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.form {
  background-color: #fff;
  width: 500px;
  padding: 20px 24px;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.form-label {
  font-weight: 600;
  margin-bottom: 8px;
}

.fa-xmark {
  font-size: 20px;
  cursor: pointer;
}

.error {
  color: red !important;
}

.status-container {
  border: 1px solid #dadada;
  padding: 4px 8px;
  border-radius: 4px;
}

.status {
  height: 10px;
  width: 10px;
  border-radius: 50%;
  border: 1px solid transparent;
}

.status-active {
  background-color: green;
}

.status-stop {
  background-color: red;
}

.modal-custom {
  background-color: #fff;
  padding: 20px 24px;
  border-radius: 4px;
  width: 400px;
}

.modal-title {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.modal-body-custom {
  padding: 20px 0;
}

.modal-footer-custom {
  display: flex;
  justify-content: end;
  gap: 8px;
}

.pagination {
  margin-bottom: 0;
}
</style>
