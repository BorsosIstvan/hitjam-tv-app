<template>
  <div class="tv-store-container">
    <!-- Fejléc -->
    <header class="tv-header">
      <h1>HITJAM <span class="tv-badge">TV STORE</span></h1>
      <p class="subtitle">Saját fejlesztésű Android TV alkalmazások letöltése V1.0.0</p>
    </header>

    <!-- Fő tartalom -->
    <main class="tv-main">
      <div class="app-card">
        <div class="app-icon">📻</div>
        <div class="app-details">
          <h2>HitJam Radio TV</h2>
          <p>Verzió: 1.0.0 (Stabil) | Méret: ~3.5 MB</p>
          <p class="description">Élő rádióadás közvetlenül az Android TV stickedre optimalizálva, teljes távirányító-támogatással.</p>
        </div>

        <!-- A TV-BARÁT LETÖLTŐ GOMB -->
        <a 
          ref="downloadButton"
          href="./PyClip.apk" 
          download="PyClip.apk"
          class="tv-download-btn"
        >
          📥 TELEPÍTÉS (PyClip.apk LETÖLTÉSE)
        </a>
      </div>
    </main>

    <!-- Lábléc infó a TV stickhez -->
    <footer class="tv-footer">
      <p>💡 Tipp: A letöltés után a <b>TV Bro</b> böngésző automatikusan felajánlja a telepítést!</p>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const downloadButton = ref(null)

onMounted(() => {
  // Amikor az oldal betölt a TV-n, a fókusz AZONNAL a letöltés gombra ugrik.
  // Így a felhasználónak csak az OK gombot kell megnyomnia a távirányítón.
  if (downloadButton.value) {
    downloadButton.value.focus()
  }
})
</script>

<style scoped>
/* Teljes képernyős TV dizájn (10-foot UI) */
.tv-store-container {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(135deg, #0f172a, #1e1b4b);
  color: #f8fafc;
  font-family: 'Segoe UI', Roboto, sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  box-sizing: border-box;
  padding: 60px;
  overflow: hidden;
}

/* Fejléc stílusok */
.tv-header {
  text-align: center;
}
.tv-header h1 {
  font-size: 3.5rem;
  margin: 0;
  letter-spacing: 2px;
  text-shadow: 0 4px 10px rgba(0,0,0,0.5);
}
.tv-badge {
  font-size: 1.5rem;
  background: #2563eb;
  padding: 6px 16px;
  border-radius: 20px;
  vertical-align: middle;
}
.subtitle {
  font-size: 1.5rem;
  color: #94a3b8;
  margin-top: 10px;
}

/* Alkalmazás kártya panel */
.app-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 24px;
  padding: 40px 60px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 20px;
  max-width: 600px;
  box-shadow: 0 20px 50px rgba(0,0,0,0.4);
}
.app-icon {
  font-size: 5rem;
}
.app-details h2 {
  font-size: 2.2rem;
  margin: 0;
  color: #38bdf8;
}
.app-details p {
  font-size: 1.1rem;
  color: #94a3b8;
  margin: 5px 0;
}
.description {
  font-size: 1.2rem !important;
  color: #cbd5e1 !important;
  margin-top: 15px !important;
}

/* A Hatalmas TV-s letöltő gomb alapstílusa */
.tv-download-btn {
  display: inline-block;
  font-size: 1.8rem;
  font-weight: bold;
  padding: 20px 50px;
  background-color: #1e293b;
  color: #e2e8f0;
  border: 4px solid transparent; /* Fix keret hely, hogy ne ugorjon a kép fókusznál */
  border-radius: 16px;
  text-decoration: none;
  transition: all 0.15s ease-in-out;
  outline: none;
  margin-top: 20px;
}

/* AMIKOR A TV TÁVIRÁNYÍTÓVAL RÁMÉSZ A GOMBRA */
.tv-download-btn:focus {
  background-color: #ec4899;   /* Rózsaszín kiemelés */
  border-color: #38bdf8;       /* Világoskék keret */
  color: #ffffff;
  transform: scale(1.1);       /* Kicsit nagyobb lesz */
  box-shadow: 0 0 40px rgba(236, 72, 153, 0.6);
}

/* Lábléc */
.tv-footer p {
  font-size: 1.3rem;
  color: #64748b;
  text-align: center;
}
</style>
