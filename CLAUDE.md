# SH Pulse — WiFi Speed Test

## Descripció
App de test de velocitat WiFi de marca SH Solucions. Single-page app HTML estàtica sense framework ni dependències de build.

**URL producció:** https://shpulse.vercel.app  
**GitHub:** https://github.com/shsolucions/SHPulse  
**Vercel project ID:** prj_35iD5XyayRiBHo5MjDZ5WqIgvHFO  
**Vercel team ID:** team_UTNEQNhrz9ELNWTHvHYBM79L  

## Estructura del projecte
```
SHPulse/
├── index.html       # App completa (tot en un sol fitxer: HTML + CSS + JS)
├── vercel.json      # Configuració Vercel (static deployment)
├── CLAUDE.md        # Aquest fitxer — context per a Claude Code
└── README.md        # Documentació pública
```

## Stack tècnic
- **HTML/CSS/JS** pur — zero dependències, zero build step
- **Font:** Inter (Google Fonts CDN)
- **Desplegament:** Vercel (auto-deploy en push a `main`)
- **Historial:** `localStorage` clau `shpulse_v3` (fins a 20 tests)

## Metodologia de mesura
Basada en estàndards **Ookla + Cloudflare + RFC 6349**. Només es mesuren baixada i pujada (no ping ni jitter):
- **Descàrrega:** 2 connexions TCP paral·leles + descarta primer 1.5s (TCP slow-start) → 10s
- **Pujada:** chunks de 2MB en bucle via XHR → 10s
- **Qualitat general:** calculada només amb baixada i pujada (excel·lent ≥300/100 Mbps, bona ≥100/30, correcta ≥30/10, millorable per sota)
- **Endpoints:** speed.cloudflare.com (principal) + fallbacks httpbin.org, jsdelivr, cdnjs

## Idiomes suportats (12)
Català (default), Espanyol, Anglès, Francès, Alemany, Italià, Portuguès, Neerlandès, Polonès, Suec, Romanès, Grec  
Detecció automàtica via `navigator.language`

## Identitat visual
- **Colors principals:** `#c9a84c` (or/gold), `#00d4ff` (cian descàrrega), `#a855f7` (violeta pujada), `#10b981` (verd completat)
- **Fons:** `#07080f` quasi negre
- **Tipografia:** Inter 700/800/900
- **Logo:** badge quadrat daurat amb "SH" en negre

## Com desplegar
```bash
# Qualsevol push a main fa auto-deploy via Vercel+GitHub
git add .
git commit -m "descripció del canvi"
git push origin main
```

## Tasques pendents / millores futures
- [ ] Compartir resultat (Web Share API)
- [ ] Gràfic d'evolució de l'historial
- [ ] Mode clar (light mode)
- [ ] Test programat automàtic
