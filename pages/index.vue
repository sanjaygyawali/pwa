<template>
  <Scene>
    <Camera></Camera>
    <HemisphericLight diffuse="#0FE0FF"></HemisphericLight>
    <Entity :position="[0, 0, 5]">
      <Animation property="rotation.x" :duration="5">
        <Key frame="0%" :value="0"></Key>
        <Key frame="100%" :value="Math.PI * 2"></Key>
      </Animation>
      <Animation
        property="rotation.y"
        :duration="5"
        :end="Math.PI * 2"
      ></Animation>
      <Animation
        property="rotation.z"
        :duration="5"
        :end="Math.PI * 2"
      ></Animation>
      <PointLight diffuse="#FF0000"></PointLight>
      <template v-for="x in [0, 4, -4]">
        <template v-for="y in [0, 4, -4]">
          <Box
            v-for="z in [0, 4, -4]"
            :position="[x, y, z]"
            :key="`${x},${y},${z}`"
          ></Box>
        </template>
      </template>
    </Entity>
  </Scene>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
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
