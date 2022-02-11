<template>
  <div class="container">
    <img class="avatar" :src="url" >
  </div>
</template>

<script>
export default ({
  name: "Profile",
  data: () => ({
    url: "https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxjb2xsZWN0aW9uLXBhZ2V8MXw3NjA4Mjc3NHx8ZW58MHx8fHw%3D&w=1000&q=80",
  })
})
</script>

<style>
  .container {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    background-color: white;
    position: absolute;
    right: 0;
    bottom: 0;
  }

  .avatar {
    width: 100%;
    border-radius: 50%;
  }
</style>
