<template>
  <section
    class="container vertical align-center justify-center"
    v-fit-height>
    <DaTerminal>
      <template slot="title">
        yarn watch
      </template>
      <template slot="content">
        <span class="box red">404</span><span class="red"> Failed to find the page</span>
        <br>
        <br>
        <!-- eslint-disable -->
        * ./views/{{ page }} in
        ./node_modules/babel-loader/lib?{"babelrc":false,"cacheDirectory":true,"presets":[["/home/shamun/Development/Projects/devkit/daily-app/node_modules/babel-preset-vue-app/dist/index.common.js",{"targets":{"ie":9,"uglify":true}}]]}!./node_modules/vue-loader/lib/selector.js?type=script&index=0!./pages/index.vue
        <!-- eslint-enable -->
      </template>
    </DaTerminal>
  </section>
</template>
<script>
import DaTerminal from '../components/DaTerminal.vue';

export default {
  name: 'NotFound',

  components: {
    DaTerminal,
  },

  data() {
    const paths = window.location.pathname.substr(1).split('/');
    paths[paths.length - 1] = `Da${paths[paths.length - 1].replace(/^\w/, c => c.toUpperCase())}`;

    const page = paths.join('/');

    return {
      page,
    };
  },
};
</script>

<style scoped>
.container {
  height: 100vh;
}

.terminal {
  width: 312px;
  height: 452px;
}
</style>
