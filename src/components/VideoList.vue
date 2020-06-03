<template>
      <!-- <ul>
          <li v-for="video in videos" :key="video.etag">
              {{ video.snippet.description }}
          </li>
      </ul> -->
      <ul class="list-group col-lg-4">
        <VideoListItem
            @video-select="onVideoSelect"
            :video="video" 
            v-for="video in videos" 
            :key="video.etag" 
        />
      </ul>
</template>

<script>
// function onVideoSelect(evnet) {
//     console.log(event.target)
// }
// button.addEventListener('video-select', onVideoSelect)

import VideoListItem from './VideoListItem.vue'

export default {
    name: 'VideoList',
    components: {
        VideoListItem,
    },
    props: {
        videos: Array,
    },
    methods: {
        onVideoSelect(video) {
            console.log('VL: Video Selected!', video.snippet.title)
            this.$emit('video-select', video)
        }
    }
}
</script>

<style>

</style>