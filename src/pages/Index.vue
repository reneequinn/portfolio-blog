<template>
  <Layout>
    <section class="hero">
      <h2>Hi, I'm Renee!</h2>
      <h3>I make <span class="highlight">awesome</span> web experiences</h3>
      <p class="lead">
        I'm a front-end developer with a passion for well-designed user
        experiences on the web.
      </p>
      <p>
        When I'm not coding or designing, I play video games wrangle two
        <strike>kittens</strike> cats, try to keep plants alive and cook.
      </p>
    </section>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Home',
  },
};
</script>

<style lang="scss">
.hero {
  .lead {
    margin-top: 1rem;
    margin-bottom: 1rem;
    font-size: 1.25rem;
  }
}
</style>
