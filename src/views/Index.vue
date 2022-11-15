<template>
  <div class="index">
    <p>Página inicial</p>
  </div>
</template>

<script>
export default {
  name: 'Index',
  mounted() {
    document.body.classList.add('d-flex');
    document.body.classList.add('flex-column');
    document.body.classList.add('h-100')
  },
  destroyed() {
    document.body.classList.remove('d-flex flex-column h-100')
  }
}
</script>
  