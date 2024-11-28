<template>
    <div class="container mt-4">
      <h2>Thông Tin Sách</h2>
      <p><strong>ID:</strong> {{ book.id }}</p>
      <p><strong>Tên Sách:</strong> {{ book.title }}</p>
      <p><strong>Tác Giả:</strong> {{ book.author }}</p>
      <p><strong>Năm Xuất Bản:</strong> {{ book.year }}</p>
      <img :src="book.cover" alt="cover" width="200" />
      <router-link to="/" class="btn btn-primary mt-3">Quay Lại</router-link>
    </div>
  </template>
  
  <script>
  export default {
    props: ['book'],
  };
  </script>