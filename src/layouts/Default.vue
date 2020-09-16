<template>
  <div class="layout">
    <Header />
    <slot />
  </div>
</template>

<script>
import Header from '~/components/Header';
export default {
  components: {
    Header,
  },
};
</script>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
