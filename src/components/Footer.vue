<template>
  <footer>
    <div class="container">
      <div>
        <small
          >&copy; Copyright {{ new Date().getFullYear() }} Renee Quinn</small
        >
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss">
footer {
  background: var(--bg-elevation-1);
  box-shadow: var(--box-shadow-md);
  padding: 1rem 0;
}
</style>
