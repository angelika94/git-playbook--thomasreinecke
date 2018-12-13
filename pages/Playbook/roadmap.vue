<template>
  <div>
    <section class="topics" v-if="topics">
      <!--<span tabindex="0" v-for="(topic, idx) in topics" :key="idx" class="tag" @keyup.enter="searchTopic(topic)" @click="searchTopic(topic)">{{topic}}</span>-->
      <span tabindex="0" v-for="(topic, idx) in topics" :key="idx" class="tag">{{topic}}</span>
    </section>

    <div class="content">
      Our Roadmap
    </div>

  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Breadcrumb from '~/components/Breadcrumb'

export default {
  data () {
    return {
      markdown: '',
      lastModified: '',
      pageConfig: {},
   //   tocItems: ConfigManager.getPages(),
      isActive: false,
      container: null,
      initialScroll: false,
      isCommentOpen: false,
      comment: '',
      likes: 0,
      dislikes: 0,
      topics: null
    }
  },
  methods: {
    handleScroll (event) {
      this.isActive = event.target.scrollTop >= 155;
    },
  },
  components: {
    Header,
    Breadcrumb
  },
  head () {
    return {
      title: 'Playbook',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'Playbook', name: 'Playbook', content: 'My custom description' }
      ]
    }
  }
}
</script>

<style>

</style>

