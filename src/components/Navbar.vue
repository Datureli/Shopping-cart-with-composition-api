<template>
  <nav class="s-sidebar__nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
</template>

<style>
.s-sidebar__nav {
  position: fixed;
  top: 0;
  overflow: hidden;
  transition: all 0.3s ease-in;
  height: 100%;
  background: #243e56;
}

/* Mobile First */
@media (min-width: 42em) {
  .s-layout__content {
    margin-left: 4em;
  }

  /* Sidebar */
  .s-sidebar__trigger {
    width: 4em;
  }

  .s-sidebar__nav {
    width: 4em;
    left: 0;
  }
}

@media (min-width: 68em) {
  .s-layout__content {
    margin-left: 15em;
  }

  /* Sidebar */
  .s-sidebar__trigger {
    display: none;
  }

  .s-sidebar__nav {
    width: 15em;
  }

  .s-sidebar__nav ul {
    top: 1.3em;
  }
}
</style>
