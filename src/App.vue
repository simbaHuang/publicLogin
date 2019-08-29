<template>
  <div id="app">
    <Row class-name="comtent" type="flex" justify="center" align="middle">
      <Col
        :xs="{ span: 20 }"
        :sm="{ span: 20 }"
        :md="{ span: 18 }"
        :lg="{ span: 16 }"
        :xl="{ span: 6 }">
        <router-view/>
      </Col>
    </Row>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
body, html{
  height: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
  height: 100%;
}
.comtent{
  height: 100%;
}
</style>
