<template>
  <div class="hello">
    <ion-header>
      <ion-toolbar>
        <ion-title>Reddit clone /r/aww</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-list>
        <ion-item 
          v-for="post in posts" 
          :key="post.data.id" 
          @click="handleClick(post.data.preview.images[0].source.url)"
        >
          <img :src="post.data.thumbnail" class="thumbnail">
          <ion-label class="label">{{post.data.title}}</ion-label>
        </ion-item>
      </ion-list>    
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  data() {
    return {
      myInput: '',
      posts: []
    }
  },
  mounted() {
    axios.get('https://www.reddit.com/r/aww.json?raw_json=1')
    .then(res => this.posts =  res.data.data.children)
  },
  methods: {
    handleClick(imageSrc) {
      // alert(this.myInput)
      this.$router.push({name: 'about', params: {imageSrc}})
    }
  }
}
</script>


<style scoped>
.thumbnail {
  width: 60px;
  height: 60px;
  border-radius: 30px;
  margin-right: 16px;
  margin-top: 10px;
  margin-bottom: 10px;
}
.thumbnail, 
.label {
  cursor: pointer;
}
</style>
