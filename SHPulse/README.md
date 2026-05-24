# SH Pulse ⚡

**Test de velocitat WiFi elegant i precís**  
by [SH Solucions](https://sh-formacions.vercel.app)

🌐 **[shpulse.vercel.app](https://shpulse.vercel.app)**

---

## Característiques

- 📶 Mesura **descàrrega, pujada, ping i jitter** en temps real
- ⏱️ **10 segons per fase** — metodologia basada en estàndards Ookla · Cloudflare · RFC 6349
- 🌍 **12 idiomes europeus** amb detecció automàtica
- 📊 **Historial persistent** (localStorage, fins a 20 tests)
- 📱 **PWA** — instal·lable com a app nativa al mòbil
- ✨ Disseny premium dark amb identitat SH Solucions
- 🚀 Zero dependències — un sol fitxer HTML

## Metodologia

| Fase | Durada | Mètode |
|------|--------|--------|
| Ping + Jitter | 10s | Mostres cada 350ms → mediana + desviació |
| Descàrrega | 10s | 2 connexions TCP paral·leles, descarta slow-start |
| Pujada | 10s | Chunks 2MB en bucle via XHR |

## Desplegament

App estàtica desplegada a Vercel. Cada push a `main` fa auto-deploy.

```bash
git add .
git commit -m "update"
git push origin main
```

---

*SH Solucions · SH Formació*
