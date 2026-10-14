# ANPS Milano – Servizi Volontari

File da caricare su GitHub: `index.html`, `firebase-config.js`, `firestore.rules` (questo ultimo serve solo per Firebase), `README.md`.
Finché in `firebase-config.js` c'è scritto INCOLLA, l'app funziona in **modalità demo** (dati solo nel browser).

## PARTE A – GitHub (5 minuti)
1. Vai su github.com → **New repository** → nome `anps-servizi` → Public → Create.
2. **Add file → Upload files**: trascina `index.html`, `firebase-config.js`, `README.md` → Commit.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch `main` / `(root)` → Save.
4. Dopo 1-2 minuti l'app è su `https://TUOUTENTE.github.io/anps-servizi/` (annota questo indirizzo).

## PARTE B – Firebase (10 minuti, gratuito col piano Spark)
1. Vai su console.firebase.google.com con un account Google → **Crea un progetto** → nome `anps-servizi` → disattiva Google Analytics → Crea.
2. **Build → Authentication → Inizia → Email/password → Abilita → Salva.**
3. **Build → Firestore Database → Crea database** → posizione `europe-west8 (Milano)` → *modalità produzione* → Crea.
4. In Firestore apri la scheda **Regole**: cancella tutto, incolla il contenuto di `firestore.rules`, **cambia `admin@esempio.it` con la tua email** → **Pubblica**.
5. **Impostazioni progetto (ingranaggio) → Le tue app → icona `</>` (Web)** → nome app → Registra → copia i valori di `firebaseConfig` (apiKey, authDomain, projectId, appId) dentro `firebase-config.js` e metti anche la tua email in `ADMIN_EMAILS`.
6. **Authentication → Impostazioni → Domini autorizzati → Aggiungi dominio**: `TUOUTENTE.github.io`.
7. Su GitHub apri `firebase-config.js` → matita ✏️ → incolla le modifiche → Commit. Attendi 1-2 minuti.

## PARTE C – Primo utilizzo
1. Apri l'app, premi **Registrati** con la **email amministratore** (sarai Amministratore).
2. Scheda **Volontari**: inserisci tutti i nominativi.
3. Ogni volontario apre il link, **Registra** (email + password) e sceglie il proprio nome.
4. Crea i servizi: i volontari li vedono subito.

## Note
- **Rimborso**: importo in euro inserito a mano dall'amministratore per ogni servizio e riconosciuto uguale a ciascun volontario partecipante; visibile solo all'amministratore nell'app e nelle statistiche (filtro Dal/Al + volontario).
- **Promemoria**: bip e avviso nel giorno prima e nel giorno del servizio, quando il volontario apre l'app. Una notifica anche ad app chiusa richiede Firebase Cloud Messaging con piano a pagamento (Blaze): possibile passo futuro.
- **PDF**: pulsante in Statistiche (rispetta i filtri). Il modulo PDF si carica da internet.
- Sicurezza: ogni volontario può solo leggere; solo l'email admin scrive (regole Firestore).
