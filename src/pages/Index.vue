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
        <strike>kittens</strike> cats, try to keep plants alive and cook. I also
        share my <g-link to="/projects">work</g-link> as well as
        <g-link to="/blog">write</g-link> about what I'm learning and working
        on.
      </p>
      <p>
        To get in touch, email me:
        <a
          href="mailto:hello@reneequinn.dev"
          target="_blank"
          rel="noopener noreferrer"
          >hello[at]reneequinn.dev</a
        >
        or find me via these links:
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
.lead {
  font-size: var(--heading-six);
  font-weight: var(--heading-weight);
}
</style>
