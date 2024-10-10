<template>
  <div class="wrapper">
      <aside class="sidebar">
        <slot name="sidebar" />
      </aside>
    <main class="main">
      <slot name="main" />
    </main>
    <footer class="footer">
      <slot name="footer" />
    </footer>
  </div>
</template>

<style>
.wrapper {
  border: 1px solid black;
}
.sidebar {
  border: 1px solid red;
}
.main {
  border: 1px solid green;
}
.footer {
  border: 1px solid blue;
}
</style>
