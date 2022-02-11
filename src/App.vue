<template>
  <div class="main">
    <div>
      <div v-for="(link, index) in links" v-bind:key="index">
        <a link :href="link.url" target="_blank" v-text="link.label" />
      </div>
    </div>
    <div footer>
      <div class="information" >
        <p class="title">@webbendr</p>
        <p v-text="description"></p>
      </div>
      <profile />
    </div>
  </div>
</template>

<script>
  import Profile from './components/Profile.vue'

  export default {
    name: 'App',
    components: {
      Profile,
    },
    data: () => ({
      links: [
        {
          label: 'tictok',
          url: 'http://google.com',
        },
        {
          label: 'instagram',
          url: 'http://google.com',
        },
        {
          label: 'snapchat',
          url: 'http://google.com',
        },
        {
          label: 'twitter',
          url: 'http://google.com',
        },
      ],
      description: "Loren ipsum dolor sit amet, consectetur adipiscing elite, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    })
  }
</script>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    background: #0101fd;
    margin: 0;
  }

  .main {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 100vh;
    padding: 15px;
  }

  a {
    font-size: 70px;
    font-weight: bold;
    text-decoration: none;
    text-transform: uppercase;
    letter-spacing: -12px;
    -webkit-text-stroke: 1px white;
  }

  a:hover {
    color: white;
  }

  footer {
    position: relative;
  }

  .information {
    width: 50%;
    color: #9a99fe;
    font-size: 14px;
  }

  .title {
    font-size: 20px;
    font-weight: bold;
    color: white;
  }
</style>
