<template>
    <li class="list-group-item">
      <div @click="toggleDetail" class="post-title">
        {{ post.title }}
      </div>
      <div v-if="showingDetail" class="post-body">
        <p>{{ post.body }}</p>
      </div>
    </li>
</template>
  
<script>
  export default {
    props: ['post'],
    data() {
      return {
        showingDetail: false,
      };
    },
    methods: {
      toggleDetail() {
        this.showingDetail = !this.showingDetail;
        if (this.showingDetail) {
          this.$emit('show-detail', this.post);
        }
      },
    },
  };
</script>
  
<style scoped>
  .post-title {
    cursor: pointer;
    font-weight: bold;
  }
  .post-title:hover {
    color: blue;
  }
  .post-body {
    margin-top: 10px;
    padding: 10px;
    background-color: #f8f9fa;
    border-radius: 5px;
  }
</style>
  