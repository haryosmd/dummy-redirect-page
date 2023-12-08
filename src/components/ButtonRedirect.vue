<template>
  <div class="button-container">
    <div class="wording-section">
      <h1 class="head-section">Login Prakerja</h1>
      <p>Ceritanya ini udah sukses verifikasi wajah.</p>
      <div class="state-action-wrapper">
        <button @click="handleChangeEnv" class="outline-primary-button">
        {{ buttonWording }}
        </button>
        <p>URL: {{env}}</p>
      </div>
    </div>
    <div class="button-wrapper">
      <button @click="redirectToKariermuSuccess" class="outline-primary-button">
        Redirect to Prakerja Karier.mu (Success)
      </button>
      <button @click="redirectToKariermuErrorWrongFace" class="outline-error-button">
        Redirect to Prakerja Karier.mu (Staging ENV)
      </button>
      <button @click="redirectToKariermuErrorLimit" class="outline-error-button">
        Redirect to Prakerja Karier.mu (Error Limit 5 times)
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      env: 'http://localhost:8080',
      isLocal: true
    }
  },
  computed: {
    buttonWording() {
      return this.isLocal ? 'Ubah Domain ke Kariermu' : 'Ubah Domain ke Local';
    }
  },
  methods: {
    redirectToKariermuSuccess() {
      window.location.href = `${this.env}/prakerja-face-recognition-status?state=OAUTHSTATECODE`;
    },
    redirectToKariermuErrorWrongFace() {
      window.location.href = 'https://prakerja.staging.karier.mu/prakerja-face-recognition-status?state=STATE-E53YF0&error=Gagal%20Verifikasi&error_code=ERRFD001&error_description=Kamu%20Sudah%20Melewati%20Batas%20Percobaan%20Verifikasi%20Wajah';
    },
    redirectToKariermuErrorLimit() {
      window.location.href = 'https://prakerja.karier.mu/prakerja-face-recognition-status?state=STATE-E53YF0&error=Gagal%20Verifikasi&error_code=ERRFD001&error_description=Kamu%20Sudah%20Melewati%20Batas%20Percobaan%20Verifikasi%20Wajah';
    },
    handleChangeEnv() {
      if (this.isLocal) {
        this.env = 'https://www.prakerja.dev.karier.mu';
      } else {
        this.env = 'http://localhost:8080';
      }
      this.isLocal = !this.isLocal;
    }
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

.state-action-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  gap: 16px;
  margin-top: 8px;
}

.button-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 14px;
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

.outline-error-button {
  font-size: 16px;
  color: #FF3838;
  border: 1px solid #FF3838;
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

.outline-error-button:hover {
  border: 1px solid #FF3838;
  background-color: #F5F8FA;
}
</style>
