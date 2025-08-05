# 💱 Vue KryptoWechsel

Ein einfaches und interaktives Vue 3-Projekt zum Umrechnen von Kryptowährungen – stilvoll umgesetzt mit **Vite**.

Diese App nutzt die [CryptoConvert API](https://github.com/coinconvert/crypto-convert), um den aktuellen Wechselkurs zwischen drei Währungen (BTC, ETH, USDT) zu berechnen.

---

## 📸 Vorschau

![Vorschau der App](./src/assets/vorschau.png) <!-- Ersetze ggf. den Pfad mit dem richtigen Bildpfad -->

---

## ⚙️ Funktionen

- 💸 Eingabe eines beliebigen Betrags
- 🔄 Auswahl von zwei Kryptowährungen (BTC, ETH, USDT)
- 📈 Umrechnung mit der CryptoConvert API
- ⭐ Speicherung von häufig genutzten Währungspaaren als Favoriten
- 🎨 Modernes, responsives Design mit leuchtenden Effekten

---

## 🧰 Tech Stack

- [Vue 3](https://vuejs.org/)
- [Vite](https://vitejs.dev/)
- [CryptoConvert](https://github.com/coinconvert/crypto-convert)
- JavaScript (ES6)
- Scoped CSS

---

## 🧪 Komponenten-Übersicht

- `Input.vue` – Zahl eingeben und Konvertierung starten
- `Selector.vue` – Währung wählen mit aktivem Zustand
- `Favourite.vue` – Favoriten anzeigen und übernehmen
- `App.vue` – Hauptkomponente und Logik

---

## 🚀 Projekt Setup

### 📦 Abhängigkeiten installieren

```bash
npm install
