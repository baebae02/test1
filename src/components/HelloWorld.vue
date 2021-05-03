<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <img src=  "require(${imgSrc})" />
    <ul>
      <li>
        <a
          href="https://blog.naver.com/bae4614"
          target="_blank"
          rel="noopener"
          >Blog</a
        >
      </li>
      <li>
        <a
          href="https://github.com/bread4614"
          target="_blank"
          rel="noopener"
          >Github</a
        >
      </li>
      <li>
        <a
          href="https://facebook.com"
          target="_blank"
          rel="noopener"
          >facebook</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    imgSrc: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
