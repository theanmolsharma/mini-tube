<template>
  <div v-if="video" class="col-md-8">
    <div class="embed-responsive embed-responsive-16by9">
      <iframe class="embed-responsive-item" :src="URLgen" />
    </div>
    <div class="detail">
      <h4>{{video.snippet.title}}</h4>
      <p>{{video.snippet.description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoPlayer",
  props: ['video'],
  computed: {
    URLgen() {
      return 'https://www.youtube.com/embed/' + this.video.id.videoId;
    }
  }
}
</script>

<style scoped>
.detail {
  background: #eee;
  margin-top: 15px;
  padding: 10px;
  border: 1px solid black;
  border-radius: 10px;
}
</style>