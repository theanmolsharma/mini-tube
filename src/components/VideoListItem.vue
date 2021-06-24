<template>
  <li class="list-group-item media" @click="videoClick">
    <img class="mr-3" :src="video.snippet.thumbnails.default.url"  alt=""/>
    <div class="media-body">{{video.snippet.title}}</div>
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ['video'],
  methods: {
    videoClick() {
      this.$emit('videoClick', this.video);
    }
  }
}
</script>

<style scoped>
li {
  display: flex;
  cursor: pointer;
  background: #eee;
}
li:hover {
  background: #ddd;
}
</style>