<template>
  <div class="button-container">
    <div class="wording-section">
      <h1 class="head-section">Login Prakerja</h1>
      <p>Ceritanya ini udah sukses verifikasi wajah.</p>
    </div>
    <button @click="redirectToCareer" class="outline-primary-button">
      Redirect to Karier.mu
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    redirectToCareer() {
      window.location.href = "https://www.karier.mu";
    },
  },
};
</script>

<style scoped>
.button-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh; /* This ensures that the container takes the full viewport height */
}

.wording-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.head-section {
  color: #006AD3;
}

.outline-primary-button {
  font-size: 16px;
  color: #006AD3;
  border: 1px solid #006AD3;
  background-color: transparent;
  cursor: pointer;
  border-radius: 20px;
  padding: 8px 16px;
  transition: background-color 0.2s, color 0.2s;
  font-family: var(--UI-text-label-1-font-family);
  font-size: var(--UI-text-label-1-font-size);
  font-style: var(--UI-text-label-1-font-style);
  font-weight: var(--UI-text-label-1-font-weight);
  letter-spacing: var(--UI-text-label-1-letter-spacing);
  line-height: var(--UI-text-label-1-line-height);
}

.outline-primary-button:hover {
  border: 1px solid #006AD3;
  background-color: #F5F8FA;
}
</style>
