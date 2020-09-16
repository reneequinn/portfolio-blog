<template>
  <div class="layout">
    <Header />
    <main class="container">
      <slot />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/Header';
import Footer from '~/components/Footer';
export default {
  components: {
    Header,
    Footer,
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
