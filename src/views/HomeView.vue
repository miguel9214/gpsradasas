<template>
  <div class="home">
    <!-- Logo en la parte superior -->
    <header class="hero text-black text-center py-4">
      <div class="container">
        <img src="@/assets/logo.jpg" alt="Logo" class="logo mb-3">
        <h1 class="display-6 mb-2">Bienvenido a Nuestro Servicio de GPS</h1>
        <p class="lead mb-4">Seguimiento en tiempo real para asegurar la seguridad de tus activos.</p>
        <router-link to="/services" class="btn btn-light btn-lg">Nuestros Servicios</router-link>
      </div>
    </header>

    <!-- Carrusel de Bootstrap dentro de un contenedor -->
    <div class="carousel-container">
      <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
        <ol class="carousel-indicators">
          <li data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active"></li>
          <li data-bs-target="#carouselExampleIndicators" data-bs-slide-to="1"></li>
          <li data-bs-target="#carouselExampleIndicators" data-bs-slide-to="2"></li>
        </ol>
        <div class="carousel-inner">
          <div class="carousel-item active">
            <img src="@/assets/slide1.jpg" class="d-block w-100" alt="Slide 1">
            <div class="carousel-caption d-none d-md-block">
              <h5>Primera Imagen</h5>
              <p>Descripción de la primera imagen.</p>
            </div>
          </div>
          <div class="carousel-item">
            <img src="@/assets/slide2.jpg" class="d-block w-100" alt="Slide 2">
            <div class="carousel-caption d-none d-md-block">
              <h5>Segunda Imagen</h5>
              <p>Descripción de la segunda imagen.</p>
            </div>
          </div>
          <div class="carousel-item">
            <img src="@/assets/slide3.jpg" class="d-block w-100" alt="Slide 3">
            <div class="carousel-caption d-none d-md-block">
              <h5>Tercera Imagen</h5>
              <p>Descripción de la tercera imagen.</p>
            </div>
          </div>
        </div>
        <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-bs-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </a>
        <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-bs-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </a>
      </div>
    </div>

    <!-- Restante del contenido (Características, CTA, etc.) -->
    <!-- Características Destacadas -->
    <!-- Sección de Características Destacadas -->
    <section class="features py-5">
      <div class="container">
        <h2 class="text-center mb-4">Características Destacadas</h2>
        <div class="row">
          <!-- Generar las cards dinámicamente -->
          <div 
            class="col-md-4" 
            v-for="(feature, index) in features" 
            :key="index"
          >
            <div class="card mb-4 hover-effect">
              <div class="card-body">
                <div class="card-icon text-center mb-3">
                  <i :class="feature.icon"></i> <!-- Usamos iconos dinámicos -->
                </div>
                <h5 class="card-title text-center">{{ feature.title }}</h5>
                <p class="card-text text-center">{{ feature.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="cta bg-light text-center py-5">
      <div class="container">
        <h2>¿Listo para comenzar?</h2>
        <p>Contáctanos para obtener más información y comenzar a usar nuestro servicio.</p>
        <router-link to="/support" class="btn btn-primary btn-lg">Contáctanos</router-link>
      </div>
    </section>

    <!-- Botón de WhatsApp -->
    <a href="https://wa.me/1234567890" class="btn-whatsapp" target="_blank" aria-label="WhatsApp">
      <img src="@/assets/whatsapp.png" alt="WhatsApp">
    </a>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  data() {
    return {
      features: [
        {
          title: 'Seguimiento en Tiempo Real',
          description: 'Monitoreo continuo de tus activos, disponible 24/7.',
          icon: 'fas fa-map-marker-alt'
        },
        {
          title: 'Historial de Rutas',
          description: 'Accede al historial completo de rutas y ubicaciones de tus activos.',
          icon: 'fas fa-route'
        },
        {
          title: 'Alertas y Notificaciones',
          description: 'Recibe alertas inmediatas sobre actividades inusuales.',
          icon: 'fas fa-bell'
        }
      ]
    };
  }
};
</script>

<style scoped>
.hero {
  text-align: center;
}

.features .card {
  border: none;
}

.cta {
  background-color: #f8f9fa;
}

.carousel-indicators {
  display: none; /* Ocultar indicadores numéricos */
}

/* Estilos para el logo */
.logo {
  max-width: 150px;
  height: auto;
}

/* Estilos para el botón de WhatsApp */
.btn-whatsapp {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: #25d366; /* Color de WhatsApp */
  border-radius: 50%;
  padding: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.btn-whatsapp img {
  width: 40px;
  height: 40px;
}

/* Limitar el ancho y altura del carrusel en pantallas grandes */
.carousel-container {
  max-width: 1200px; /* Limitar ancho máximo en pantallas grandes */
  margin: 0 auto; /* Centrar el carrusel */
  padding: 0 15px; /* Añadir un poco de padding lateral en pantallas pequeñas */
}

.carousel-inner img {
  width: 100%;
  max-height: 500px; /* Limitar altura máxima */
  object-fit: cover; /* Asegura que la imagen mantenga su proporción y se recorte si es necesario */
}

.features .card {
  border: none;
  background-color: #f8f9fa;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.features .card .card-icon {
  font-size: 40px;
  color: #007bff;
}

.features .card .card-title {
  font-size: 1.25rem;
  font-weight: bold;
  color: #343a40;
}

.features .card .card-text {
  color: #6c757d;
}

.features .card:hover {
  transform: translateY(-10px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
}

.hover-effect {
  cursor: pointer;
  transition: transform 0.3s ease-in-out;
}

.hover-effect:hover {
  transform: translateY(-10px);
}

@media (max-width: 768px) {
  .features .card {
    margin-bottom: 20px;
  }
}
</style>
