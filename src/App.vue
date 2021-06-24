<template>
  <div class="container">
    <SearchBar @newSearch="newSearch"></SearchBar>
    <div class="row">
      <VideoPlayer :video="clickedVideo"></VideoPlayer>
      <VideoList :videoList="videoList" @videoClick="clickVideo"></VideoList>
    </div>
  </div>
</template>

<script>
import axios from "axios"
import SearchBar from "@/components/SearchBar";
import VideoList from "@/components/VideoList";
import VideoPlayer from "@/components/VideoPlayer";

const API_KEY = "AIzaSyApQ16H9Cb4pK2F4fphUkWAeTEdvYikMTA";

export default {
  name: 'App',
  components: {VideoPlayer, VideoList, SearchBar},
  data() {
    return {
      videoList: [],
      clickedVideo: null
    }
  },
  methods: {
    newSearch(query) {
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          q: query,
          type: 'video',
          part: 'snippet'
        }
      }).then(response => this.videoList = response.data.items);
    },
    clickVideo(video) {
      this.clickedVideo = video;
    }
  }
}
</script>

<style>
</style>
