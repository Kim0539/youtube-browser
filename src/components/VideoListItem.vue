<template>
  <li @click="onVideoSelect" class="video-list-item list-group-item">
    <img :src="thumbnailUrl" class="mr-3" alt="youtube-thumbnail-image">
    <div class="media-body">
        {{ video.snippet.title }}
    </div>
  </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        video: Object,
    },
    methods: {
        onVideoSelect() {
            console.log('VLI: Selected')
            this.$emit('video-select', this.video)
        }
    },
    computed: {
        // 함수지만 네이밍 명사형 => 결국 리턴되는 값으로 사용되기 때문.
        thumbnailUrl() {
            return this.video.snippet.thumbnails.default.url
        }
    }
}
</script>

<style>
li.video-list-item {
    display: flex;
    cursor: pointer;
}
li.video-list-item:hover {
    background-color: #eee;
}
.media-body {
    margin: auto 0;
}
</style>