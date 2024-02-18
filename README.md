# Tailwind

Installare Tailwind CSS in un progetto React:

### Crea il tuo progetto

Inizia creando un nuovo progetto React con Vite utilizzando il seguente comando nel terminale:

    npm create vite@latest my-project -- --template react

Dove **"my-project"** è il nome del tuo progetto. Successivamente, entra nella directory del tuo progetto:

    cd my-project

### Installa Tailwind CSS

Utilizza npm per installare Tailwind CSS e le sue dipendenze:

    npm install -D tailwindcss postcss autoprefixer

Di seguito, utilizza il seguente comando per generare i file `tailwind.config.js` e `postcss.config.js`:

    npx tailwindcss init -p

### Configura i percorsi dei template

Modifica il file `tailwind.config.js` per includere i percorsi di tutti i tuoi file di template. Aggiungi i percorsi dei tuoi file HTML e dei file di codice **(JSX/TSX)** nel campo content:

    export default {
    content: [
        "./index.html",
        "./src/**/*.{js,jsx,ts,tsx}",
    ],
    theme: {
        extend: {},
    },
    plugins: [],
    };

### Aggiungi le direttive Tailwind al tuo CSS

Modifica il tuo file CSS principale (tipicamente **index.css** o **App.css**) aggiungendo le direttive Tailwind:

    @tailwind base;
    @tailwind components;
    @tailwind utilities;

oppure

    @import 'tailwindcss/base';
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';

### Avvia il processo di build

Avvia il processo di build del progetto utilizzando il seguente comando:

npm run dev

### Utilizza Tailwind nel tuo progetto

Ora puoi iniziare ad utilizzare le classi di utilità di Tailwind CSS nei tuoi file `JSX/TSX` per stilizzare il contenuto del tuo progetto React.

            <div id="box" className="bg-gradient-to-bl to-blue-800 from-red-800 rotate-45">x è {x}</div>

### Utilizzo di Template Literals su un progetto React con Tailwind CSS

L'utilizzo di template literals in combinazione con React e Tailwind CSS consente agli sviluppatori di creare componenti dinamici e ben stilizzati. Template literals sono una caratteristica di JavaScript che consente l'inserimento di espressioni JavaScript all'interno di stringhe delimitate da backtick (`), consentendo la generazione dinamica di classi CSS e attributi HTML all'interno dei componenti React.

    // Importa il file CSS per lo stile aggiuntivo
    import "./NavBar.css";
    // Importa il componente Link
    import Link from "./Link";

    // Definizione del componente NavBar che utilizza React, Tailwind CSS e template literals
    function NavBar() {
        // Variabili per lo stile e la logica dinamica
        const x = 6;
        const img = "vite";
        const imgStyle = {
            height : "200px",
            borderRadius : "30px"
        }

        // Renderizza il componente NavBar
        return (
            <>
                {/* Elemento div con stili di Tailwind CSS e rotazione condizionale utilizzando template literals */}
                <div id="box" className={`bg-gradient-to-bl to-blue-800 from-red-800 rotate-45 ${x < 10 ? "rotate-45" : "rotate-180"}`}>
                    x è {x}
                </div>

                {/* Immagine con stile personalizzato */}
                {<img style={imgStyle} src={`/${img}.svg`} alt="" />}

                {/* Lista non ordinata di Link */}
                <ul>
                    <li>
                        <Link>Qwerty</Link>
                    </li>
                    <li>
                        <Link>Contatti</Link>
                    </li>
                    <li>
                        <Link>About</Link>
                    </li>
                </ul>
            </>
        );
    }

    // Esporta il componente NavBar
    export default NavBar;

Utilizziamo template literals per integrare dinamicamente variabili JavaScript, condizioni e espressioni all'interno delle stringhe di classi CSS. Questo ci consente di applicare stili condizionali e dinamici ai nostri componenti React utilizzando Tailwind CSS in modo efficiente e flessibile.