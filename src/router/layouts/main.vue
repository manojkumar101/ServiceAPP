<template>
  <div id="appRoot">
    <template v-if="!$route.meta.public">
      <Pageheader></Pageheader>
      <div class="pageWrapper">
        <router-view></router-view>
        <slot />
      </div>
 

      <!-- App Footer -->
      <!-- <Pagefooter></Pagefooter> -->
    </template>
    <template v-else>
      <transition>
        <keep-alive>
          <router-view :key="$route.fullpath"></router-view>
        </keep-alive>
      </transition>
    </template>
   
  </div>
</template>
<script>
import Pageheader from '@/src/components/Pageheader'
// import Pagefooter from '@/src/components/Pagefooter'

export default {
  components: {
    Pageheader,
    // Pagefooter,
  },
  data: () => ({
  
  }),

  computed: {},

  created() {},
  methods: {
    
  },
}
</script>

<style lang="stylus">
.pageWrapper {
  min-height: calc(100vh - 64px - 50px - 81px);
}
</style>
