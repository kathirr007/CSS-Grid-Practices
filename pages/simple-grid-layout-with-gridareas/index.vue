<script setup lang="ts">
useHead({
  title: 'Simple grid layout | Grid areas',
})
</script>

<template>
  <div class="simple-grid-layout">
    <header>
      <h1>Grid areas are awesome</h1>
    </header>
    <main class="main-content">
      Main content
    </main>
    <aside class="sidebar">
      Sidebar
    </aside>
    <footer>
      Footer
    </footer>
  </div>
</template>

<style scoped lang="scss">
/* basic styling so we can
   see what's going on */

* {
  box-sizing: border-box;
}

header,
.main-content,
.sidebar,
footer {
  padding: 2em;
  display: grid;
  align-items: center;
}

header {
  background: #41d3bd;
}
.main-content {
  background: #de6449;
}
.sidebar {
  background: #407899;
}
footer {
  background: #694d75;
}

/* ======================
   Demo stuff starts here
   ========================*/

.simple-grid-layout {
  margin: 0;
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1.5rem 1fr 1.5rem;
  grid-template-areas:
    'header header header'
    'main main main'
    'side side side'
    'footer footer footer';

  header {
    grid-area: header;
  }
  .main-content {
    grid-area: main;
  }
  .sidebar {
    grid-area: side;
  }
  footer {
    grid-area: footer;
  }

  @media only screen and (min-width: 640px) {
    grid-template-areas:
      'header header header'
      '. main .'
      '. side .'
      'footer footer footer';
  }

  @media only screen and (min-width: 860px) {
    grid-template-columns: minmax(1.5em, 1fr) minmax(650px, 960px) 450px minmax(
        1.5em,
        1fr
      );
    grid-template-areas:
      'header header header header'
      '. main side .'
      'footer footer footer footer';
  }
}
</style>
