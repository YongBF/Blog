<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        {{title}}
      </h1>
      <p>{{body}}</p>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default {
  data() {
    return {
      title: 'blog1',
      body: 'default body'
    }
  },
  //first commit test
  async asyncData(context: {param: Object | undefined, req: any, res: Object}) {
    const {param, req, res} = context
    console.log('this is console', res)
    let body = await new Promise((resovle) => {
      setTimeout(() => {
        resovle('this is body')
      }, 1000);
    })
    return { body }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
