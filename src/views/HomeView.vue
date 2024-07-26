<script setup>
import { onMounted } from 'vue'
import { PassageUser } from '@passageidentity/passage-elements/passage-user'
import { useAuthStore } from '@/stores/auth'

const authStore = useAuthStore()

const getUserInfo = async () => {
  try {
    const authToken = localStorage.getItem('psg_auth_token')
    const passageUser = new PassageUser(authToken)
    const user = await passageUser.userInfo(authToken)
    if (user) {
      await authStore.setToken(authToken)
    } else {
      authStore.unsetToken()
    }
  } catch (error) {
    authStore.unsetToken()
  }
}

onMounted(() => {
  getUserInfo()
})
</script>

<template>
  <div class="page">
    <header class="header">
      <h1 class="title">McQueen Garagem</h1>
      <p class="subtitle">Encontre o carro dos seus sonhos</p>
    </header>

    <section class="hero">
      <h2 class="hero-title">Bem-vindo!</h2>
      <p class="hero-description">Explore nossa coleção exclusiva de veículos e acessórios.</p>
      <button class="cta-button">Começar Agora</button>
    </section>

    <section class="testimonials">
      <h2 class="testimonials-title">O que nossos clientes dizem</h2>
      <div class="testimonial-container">
        <div class="testimonial">
          <p class="testimonial-text">“A McQueen Garagem transformou minha experiência de compra de veículos! Atendimento excepcional e uma vasta seleção de carros.”</p>
          <p class="testimonial-author">- João Silva</p>
        </div>
        <div class="testimonial">
          <p class="testimonial-text">“Encontrei o carro dos meus sonhos com a ajuda da equipe da McQueen. Altamente recomendados!”</p>
          <p class="testimonial-author">- Maria Oliveira</p>
        </div>
        <div class="testimonial">
          <p class="testimonial-text">“Excelentes serviços e suporte ao cliente. A McQueen Garagem é a minha primeira escolha para qualquer necessidade automobilística.”</p>
          <p class="testimonial-author">- Carlos Pereira</p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem;
  min-height: 100vh;
  box-sizing: border-box;
}

.header {
  text-align: center;
  margin-bottom: 2rem;
  width: 100%;
}

.title {
  font-size: 2.5rem;
  color: #000;
  margin: 0;
  font-weight: 700;
}

.subtitle {
  font-size: 1.25rem;
  color: #6c757d;
  margin: 0;
}

.hero {
  text-align: center;
  background: #fff;
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  padding: 2rem;
  max-width: 800px;
  margin-bottom: 2rem;
  width: 100%;
}

.hero-title {
  font-size: 2rem;
  color: #000;
  margin-bottom: 1rem;
}

.hero-description {
  font-size: 1.125rem;
  color: #495057;
  margin-bottom: 1.5rem;
}

.cta-button {
  background-color: #000;
  color: #fff;
  border: none;
  border-radius: 25px;
  padding: 0.75rem 2rem;
  font-size: 1.125rem;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
}

.cta-button:hover {
  background-color: #333;
  transform: scale(1.05);
}

.testimonials {
  text-align: center;
  width: 100%;
  max-width: 1200px;
  margin-bottom: 2rem;
}

.testimonials-title {
  font-size: 2rem;
  color: #000;
  margin-bottom: 1.5rem;
  font-weight: 700;
}

.testimonial-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.testimonial {
  background-color: #fff;
  color: #000;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 600px;
  width: 100%;
  transition: background-color 0.3s, transform 0.3s;
}

.testimonial:hover {
  background-color: #f0f0f0;
  transform: scale(1.03);
}

.testimonial-text {
  font-size: 1rem;
  color: #495057;
  margin-bottom: 0.5rem;
}

.testimonial-author {
  font-size: 0.875rem;
  color: #6c757d;
  font-style: italic;
}

@media (max-width: 1200px) {
  .title {
    font-size: 2rem;
  }

  .subtitle {
    font-size: 1rem;
  }
}

@media (max-width: 992px) {
  .hero-title {
    font-size: 1.75rem;
  }

  .hero-description {
    font-size: 1rem;
  }

  .cta-button {
    font-size: 1rem;
    padding: 0.5rem 1.5rem;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 1.5rem;
  }

  .cta-button {
    font-size: 0.875rem;
    padding: 0.5rem 1rem;
  }

  .testimonial-container {
    flex-direction: column;
  }
}
</style>
