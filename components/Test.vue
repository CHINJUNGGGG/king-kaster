<template>
  <div>
    <no-ssr>
      <!-- important to add no-ssr-->

      <carousel :autoplay="true" :nav="false">
        <img src="https://placeimg.com/200/200/any?1" />

        <img src="https://placeimg.com/200/200/any?2" />

        <img src="https://placeimg.com/200/200/any?3" />

        <img src="https://placeimg.com/200/200/any?4" />
      </carousel>
    </no-ssr>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped></style>
