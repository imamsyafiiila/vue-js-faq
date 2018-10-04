<template>
  <div>
    <header>
    	<h1>FAQ Template</h1>
    </header>
    <router-view></router-view>
  </div>
</template>

<script>
import listFaq from './components/listFaq.vue';

export default {
  components: {
    'list-faq': listFaq
  },
  data () {
    return {
    }
  }
}
</script>

<style>
</style>
