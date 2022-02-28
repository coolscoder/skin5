<template>
  <div class="container">
    <img class="avatar" :src="url" >
    <div data-emblem>
      <slot v-for="n in 4" :key="n">{{name +' &middot; '}}</slot>
    </div>
  </div>
</template>

<script>
export default ({
  name: "Profile",
  data: () => ({
    url: "https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxjb2xsZWN0aW9uLXBhZ2V8MXw3NjA4Mjc3NHx8ZW58MHx8fHw%3D&w=1000&q=80",
    name: 'webbendr',
  }),
  mounted: () => {
    this.startEmblem('[data-emblem]')
  },
  methods: {
    startEmblem: (el, str) => {
			var element = document.querySelector(el)
			var text = str ? str : element.innerHTML
			element.innerHTML = ""
			for (var i = 0; i < text.length; i++) {
				var letter = text[i]
				var span = document.createElement("span")
				var node = document.createTextNode(letter)
				var r = (360 / text.length) * i
				var x = (Math.PI / text.length).toFixed(0) * i
				var y = (Math.PI / text.length).toFixed(0) * i
				span.appendChild(node)
				span.style['-webkit-transform'] =
					"rotateZ(" + r + "deg) translate3d(" + x + "px," + y + "px,0)"
				span.style['transform'] =
					"rotateZ(" + r + "deg) translate3d(" + x + "px," + y + "px,0)"
				element.appendChild(span)
			}
		}
  }
})
</script>

<style lang="scss">
  .container {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    background-color: transparent;
    position: absolute;
    right: 0;
    bottom: 0;
  
    .avatar {
      width: 100px;
      border-radius: 50%;
      margin: 40px;
    }

    [data-emblem] {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate3d(-50%,-50%,0) rotateZ(0);
      width: 11rem;
      height: 11rem;
      border-radius: 50%;
      color: #fff;
      animation: spinZ 20s linear infinite;
      text-align: center;

      span {
        position: absolute;
        display: inline-block;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        text-transform: uppercase;
        font-size: 0.9rem;
        font-family: courier, helvetica, arial, sans-serif;
        transition: all 0.5s cubic-bezier(0, 0, 0, 1);
        color: #fff;
      }

      @keyframes spinZ {
        0% {
          transform: translate3d(-50%,-50%,0) rotateZ(360deg);
        }
        100% {
          transform:  translate3d(-50%,-50%,0) rotateZ(0deg);
        }
      }
    }
  }
</style>
