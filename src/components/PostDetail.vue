<template>
    <div v-if="post" class="post-detail card mt-3">
      <div class="card-body">
        <h3 class="card-title">{{ post.title }}</h3>
        <p class="card-text">{{ post.body }}</p>
      </div>
    </div>
</template>
  
<script>
  export default {
    props: ['post'],
  };
</script>
  
<style scoped>
  .post-detail {
    margin-top: 20px;
  }
</style>
  