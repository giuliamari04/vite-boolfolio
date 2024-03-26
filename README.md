## Myportfolio
# Benvenuti nel mio Portfolio!

Ciao, sono Giulia, un appassionata sviluppatrice web con una passione per la creazione di esperienze digitali coinvolgenti e intuitive. Con un'esperienza ancora da junior nel settore, mi dedico a trasformare idee creative in progetti web straordinari.

## Chi sono?

- 🚀 Creativa e innovativa, mi piace affrontare sfide complesse e trovare soluzioni efficaci.
- 💻 Esperta in HTML, CSS, JavaScript e altri linguaggi e tecnologie web moderni. Conosco Vue e mi sto studiando React
- 🌐 Mi vorrei specializzare nello sviluppo front-end e back-end, garantendo prestazioni ottimali e una user experience impeccabile.
- 🎨 Appassionata di design e UX/UI, mi impegno a creare siti web esteticamente piacevoli e funzionali.
- 📈 Sempre alla ricerca di nuove tecnologie e tendenze per migliorare continuamente le mie competenze e offrire soluzioni all'avanguardia.

## Cosa offro?

- ✔️ Siti web responsive e ottimizzati per tutti i dispositivi e le piattaforme.
- ✔️ Interfacce utente intuitive e facili da usare per massimizzare l'engagement degli utenti.
- ✔️ Soluzioni personalizzate e flessibili per soddisfare le esigenze specifiche dei clienti.
- ✔️ Assistenza post-lancio e supporto tecnico per garantire il successo a lungo termine dei progetti.

## Contattami

Sono sempre aperta a nuove opportunità di collaborazione e progetti interessanti. Non esitate a contattarmi per discutere delle vostre idee o per qualsiasi altra informazione.

- 📧 Email: [giuliamari04@gmail.com](giuliamari04@gmail.com)
- 🔗 LinkedIn: [linkedin-giulia-mariano](https://www.linkedin.com/in/giulia-mariano-3a1a052b1/?profileId=ACoAAEsT6-kBPoZ0b8W0FMHdVkm-dAhKvYBFV1I)

Grazie per aver visitato il mio portfolio! Spero di avere l'opportunità di lavorare insieme a voi.

## .

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
## consegna esercizio 
Esercizio di oggi: Laravel Boolfolio - API
nome repo: vite-boolfolio
Ciao ragazzi,
continuiamo a lavorare sul codice dei giorni scorsi, ma in una nuova repo.
L’esercizio di oggi è suddiviso in milestone ed è importante che ne seguiate l’ordine.
# Milestone 1
Iniziamo ad occuparci della parte front-office della nostra applicazione: creiamo un nuovo progetto Vue 3 con Vite e installiamo axios.
Installiamo vue router e creiamo il file router.js con le rotte (almeno  home, projects, singolo progetto e fallback route)
# Milestone 2
Nel componente relativo alla lista dei progetti della nostra Vue App facciamo una chiamata API all’endpoint costruito nel progetto Laravel  e recuperiamo tutti i progetti dal nostro back-end.
Stampiamo in console i risultati e verifichiamo di ricevere i dati correttamente. Poi stampiamoli in pagina
 # Milestone 3
Creiamo un nuovo componente ProjectCard, che corrisponde ad una card per visualizzare un progetto. Utilizziamo questo componente per visualizzare tutti i progetti ricevuti tramite API.
# Milestone 4
Creiamo un nuovo componente es. ProjectDetail che corrisponde alla rotta per visualizzare il singolo progetto completo di technologies e Type. Utilizziamo questo componente per visualizzare i dati ricevuti tramite API che recupera il singolo progetto.
Creiamo anche un componente NotFound per la rotta di fallback.
# Bonus:
Gestire la paginazione dei risultati nella pagina dei progetti
Creare una barra di navigazione in un componente header e un componente per il footer

watch: {
        '$route.params.slug': function (newSlug, oldSlug) {
                if (newSlug !== oldSlug) {
                this.getOneProject();
            }
        }
    },