<template>
  <div class="container">
    <header>
      <!-- Queremos contenido de la cabecera aquí. -->
      <slot name="header"></slot>
    </header>
    <main>
      <!-- Queremos contenido principal aquí. -->
      <slot></slot>
    </main>
    <footer>
      <!-- Queremos contenido de pie de página aquí. -->
      <slot name="footer"></slot>
    </footer>
  </div>
</template>


<script>
export default {
  name: "base-layout"
};
</script>