<template>
  <div v-if="video" class="col-lg-8">
    <div class="embed-responsive embed-responsive-16by9">
      <iframe 
        class="embed-responsive-item" 
        :src="videoUrl" 
        allowfullscreen>
      </iframe>
    </div>
    <div class="details">
      <!-- innerHTML --> 
      <!-- <h4 v-html="video.snippet.title"></h4> -->
      <!-- innerText -->
      <!-- <h4 v-text="video.snippet.title"></h4> -->
      <h4>{{ video.snippet.title }}</h4>
      <p>{{video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
    name: 'VideoDetail',
    props: {
      video: Object,
    },
    computed: {
      videoUrl() {
        return `https://youtube.com/embed/${this.video.id.videoId}`
      }
    },
}
</script>

<style>
div.details{
  margin-top: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}
</style>