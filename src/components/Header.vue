<template>
  <header>
    <div class="container flex-container">
      <h2><g-link to="/">Renee Quinn</g-link></h2>
      <div class="switch-container">
        <label for="theme-checkbox" class="theme-switch">
          <input type="checkbox" id="theme-checkbox" @change="toggleTheme" />
          <div class="slider round"></div>
          <svg
            class="sun"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"
              clip-rule="evenodd"
            ></path>
          </svg>
          <svg
            class="moon"
            fill="currentColor"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
            ></path>
          </svg>
        </label>
      </div>
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
    toggleTheme() {
      document.body.classList.toggle('dark-theme');
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

// theme toggle styles
.switch-container {
  display: flex;
  align-items: center;
  margin-left: auto;
  margin-right: 1rem;
}

.theme-switch {
  display: inline-block;
  position: relative;
  width: 60px;
  height: 34px;

  &:hover {
    .slider {
      background: var(--primary-dk);
    }
  }
  .slider {
    background: var(--primary);
    cursor: pointer;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    transition: 0.4s;

    &:before {
      background: var(--bg-elevation-1);
      content: '';
      width: 26px;
      height: 26px;
      z-index: 10;
      position: absolute;
      left: 4px;
      top: 50%;
      transform: translateY(-50%);
      transition: 0.4s;
    }

    &.round {
      border-radius: 34px;
    }

    &.round:before {
      border-radius: 50%;
    }
  }

  .sun,
  .moon {
    cursor: pointer;
    position: absolute;
    width: 22px;
    height: 22px;
    top: 50%;
    transform: translateY(-50%);
    fill: var(--bg-elevation-1);
  }

  .sun {
    left: 6px;
  }

  .moon {
    right: 6px;
  }

  input {
    display: none;
  }

  input:checked + .slider:before {
    top: 50%;
    transform: translateX(26px) translateY(-50%);
  }
}

// hamburger button styles
.menu-btn {
  padding: 0.5rem;
  display: flex;
  align-content: center;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  background: transparent;
  color: var(--font-color);

  svg {
    fill: currentColor;
  }

  &:hover {
    background: var(--background);
    color: var(--primary-dk);
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
