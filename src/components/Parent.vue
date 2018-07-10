<template>
    <div class="parent">
      <h2>Slider</h2>
      <transition :name="transitionName">
        <router-view class="child-view"></router-view>
      </transition>
    </div>
</template>

<script>
export default {
  name: 'Parent',
  props: {
    msg: String
  },
  data () {
    return {
      transitionName: 'slide-left'
    }
  },
  beforeRouteUpdate (to, from, next) {
      console.log(to.path.split('/'))
      console.log(from.path.split('/'))
    const toDepth = to.path.split('/').length
    const fromDepth = from.path.split('/').length
    this.transitionName = toDepth < fromDepth ? 'slide-right' : 'slide-left'
    next()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.parent {
    background-color: #41b88336;
}

</style>
