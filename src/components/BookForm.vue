<template>
    <div class="container mt-4">
      <h2>{{ isEdit ? "Chỉnh Sửa Sách" : "Thêm Mới Sách" }}</h2>
      <form @submit.prevent="saveBook">
        <div class="mb-3">
          <label>Tên Sách:</label>
          <input v-model="book.title" type="text" class="form-control" required />
        </div>
        <div class="mb-3">
          <label>Tác Giả:</label>
          <input v-model="book.author" type="text" class="form-control" required />
        </div>
        <div class="mb-3">
          <label>Năm XB:</label>
          <input v-model="book.year" type="number" class="form-control" required />
        </div>
        <div class="mb-3">
          <label>Ảnh Bìa:</label>
          <input v-model="book.cover" type="url" class="form-control" required />
        </div>
        <button type="submit" class="btn btn-success">Lưu</button>
        <button @click="$emit('cancel')" type="button" class="btn btn-secondary">Hủy</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    props: ['book', 'isEdit'],
    methods: {
      saveBook() {
        this.$emit('saveBook', this.book);
      },
    },
  };
  </script>