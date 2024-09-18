<template>
    <div class="container py-5">
      <h1 class="text-center mb-5">Soporte Técnico</h1>
      <p class="text-center">¿Necesitas ayuda? Contáctanos <a href="mailto:soporte@gps.com">aquí</a>.</p>
      <form class="mt-4">
        <div class="mb-3">
          <label for="email" class="form-label">Correo electrónico</label>
          <input type="email" class="form-control" id="email" placeholder="Tu correo">
        </div>
        <div class="mb-3">
          <label for="message" class="form-label">Mensaje</label>
          <textarea class="form-control" id="message" rows="4" placeholder="Tu mensaje"></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Enviar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Support',
  };
  </script>
  