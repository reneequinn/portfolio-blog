<template>
  <header>
    <div class="container flex-container">
      <h1><g-link to="/">Renee Quinn</g-link></h1>
      <nav>
        <ul>
          <li>
            <g-link to="/">Home</g-link>
          </li>
          <li>
            <g-link to="/about">About</g-link>
          </li>
          <li>
            <g-link to="/projects">Projects</g-link>
          </li>
          <li>
            <g-link to="/blog">Blog</g-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss">
header {
  background: var(--bg-elevation-1);
  font-family: var(--heading-font);
  box-shadow: var(--box-shadow-md);
  position: sticky;
  top: 0;
  padding: 1rem 0;

  a {
    color: var(--font-color);
    text-decoration: none;
    letter-spacing: var(--letter-spacing);
    padding: 0.25rem 0;
    transition: color 300ms ease-out;
    transition: border 200ms ease-out;

    &:hover {
      color: var(--primary-dk);
      border-bottom: 2px var(--primary-dk) solid;
    }
  }

  h1 a {
    font-size: var(--nav-heading);
    padding: 0;
  }

  ul {
    display: flex;
    align-items: center;

    li {
      margin: 0 1rem;

      &:last-of-type {
        margin-right: 0;
      }
    }
  }
}
</style>
