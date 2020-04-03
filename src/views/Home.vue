<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <GridListView>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
      <div class="grid--list--element">
        <h2>Headline 1</h2>
        <p>Some text..</p>
      </div>
    </GridListView>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import GridListView from '@/components/grid-list-view.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
    GridListView
  }
}
</script>
