<template>
  <section class="text-center my-5">
    <h2 class="display-5"><strong>{{ title }}</strong></h2>
    <p>{{ time }}</p>
  </section>
</template>

<script>
export default {
  name: 'DataTitle',
  props: ['title', 'time']
}
</script>

<style>

</style>