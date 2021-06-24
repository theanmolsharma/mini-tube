<template>
  <ul class="list-group col-md-4">
    <VideoListItem v-for="video in videoList" :video="video" :key="video.etag" @videoClick="videoClick">
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "@/components/VideoListItem";
export default {
  name: "VideoList",
  components: {VideoListItem},
  props: ['videoList'],
  methods: {
    videoClick(video) {
      this.$emit('videoClick', video);
    }
  }
}
</script>

<style scoped>
</style>