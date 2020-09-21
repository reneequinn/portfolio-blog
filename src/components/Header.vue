<template>
  <header>
    <div class="container flex-container">
      <h2><g-link to="/">Renee Quinn</g-link></h2>
      <button
        class="menu-btn"
        @click="toggleMenu"
        :class="{ open: isOpen }"
        aria-label="menu"
        aria-controls="navigation"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          width="24"
          height="24"
        >
          <g class="menu-icon">
            <path
              class="heroicon-ui"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
            />
          </g>
          <g class="close-icon">
            <path
              class="heroicon-ui"
              d="M16.24 14.83a1 1 0 0 1-1.41 1.41L12 13.41l-2.83 2.83a1 1 0 0 1-1.41-1.41L10.59 12 7.76 9.17a1 1 0 0 1 1.41-1.41L12 10.59l2.83-2.83a1 1 0 0 1 1.41 1.41L13.41 12l2.83 2.83z"
            />
          </g>
        </svg>
      </button>
      <nav id="navigation" :class="{ open: isOpen }">
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
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style lang="scss">
header {
  background: var(--bg-elevation-1);
  font-family: var(--heading-font);
  box-shadow: var(--box-shadow-md);
  position: sticky;
  top: 0;
  padding: 1rem 0;

  .flex-container {
    flex-wrap: wrap;
  }

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

  h2 {
    margin: 0;
    font-size: var(--nav-heading);

    a {
      padding: 0;
    }
  }
}

// hamburger button styles
.menu-btn {
  padding: 0.5rem;
  display: flex;
  align-content: center;
  border: var(--font-color) 2px solid;
  border-radius: 5px;
  cursor: pointer;

  svg {
    fill: currentColor;
  }

  &:hover {
    background: var(--bg-elevation-2);
    color: var(--primary-dk);
    border-color: var(--primary-dk);
  }

  &.open {
    .menu-icon {
      opacity: 0;
      transform: scale(0);
    }

    .close-icon {
      opacity: 1;
      transform: scale(1);
    }
  }

  .menu-icon {
    transform-origin: center;
    opacity: 1;
    transform: scale(1);
    transition: transform 0.4s ease-in-out, opacity 0.2s;
  }

  .close-icon {
    transform-origin: center;
    opacity: 0;
    transform: scale(0);
    transition: transform 0.3s ease-in-out, opacity 0.5s;
  }
}

// media queries
nav {
  display: none;

  &.open {
    display: block;
    flex-grow: 1;
    width: 100%;
  }
  ul {
    display: block;

    li {
      margin: 1rem 0;
    }
  }
}

@media (min-width: 640px) {
  nav {
    display: inline-block;
    width: auto;
    margin-left: auto;

    &.open {
      width: auto;
      flex-grow: initial;
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

  .menu-btn {
    display: none;
  }
}
</style>
