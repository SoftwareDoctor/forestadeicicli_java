### L’avventura del Developer Java attraverso la Foresta dei Cicli e l’algoritmo della ricerca binaria.

# Introduzione
Benvenuto alla Foresta dei Cicli! Questo è un gioco Java che ti metterà alla prova nell'esplorare una foresta piena di trappole e ostacoli. Qui troverai le istruzioni su come avviare l'applicativo e le tecnologie utilizzate.

# Avvio dell'Applicativo
Per avviare l'applicativo, segui questi passaggi:
- Assicurati di avere Java installato sul tuo computer.
- Clona questo repository sul tuo computer.

# Tecnologie Utilizzate
L'applicativo è stato sviluppato utilizzando Java. Le principali tecnologie utilizzate sono:
- Java
- Spring Boot
- JPA Hibernate
- Lombok
- H2 Database
- Postman

# Struttura del Progetto
- **ForestaGioco**: Rappresenta l’entità foresta del gioco 
- **GiocoService**: Gestisce la logica di gioco, inclusi i tentativi rimanenti e il superamento degli ostacoli utilizzando l'algoritmo di ricerca binaria
- **GiocoRepository**: Fornisce metodi per salvare e recuperare le informazioni del gioco dal database
- **GiocoController**: Gestisce le richieste HTTP e mappa le API REST per interagire con il gioco

# Come funziona l’algoritmo della ricerca binaria?
L'algoritmo di ricerca binaria viene utilizzato nel metodo `cercaPercorsoSicuro(ForestaGioco forestaGioco, int inizio, int fine)`. Questo metodo cerca la posizione più sicura lungo l'asse Y della foresta, prendendo in considerazione l'asse X come parametro di ricerca.

Ecco come funziona:
- **Inizializzazione del ciclo while**: Il metodo inizia con un ciclo while che continua fintanto che l'indice `inizio` è minore di `fine`. Questo indica che c'è ancora un intervallo da esplorare lungo l'asse Y.
- **Calcolo del punto medio**: All'interno del ciclo, viene calcolato l'indice medio dell'intervallo attuale utilizzando la formula `medio = inizio + (fine - inizio) / 2`. Questo punto medio viene utilizzato per dividere l'intervallo in due parti.
- **Controllo della presenza di un ostacolo**: Viene verificato se nella posizione media lungo l'asse X (precisamente nella prima colonna, ovvero `forestaGioco.getMappa()[medio][0]`) c'è un ostacolo. Se non c'è un ostacolo (cioè se `!forestaGioco.getMappa()[medio][0]` è vero), significa che è possibile proseguire in avanti per trovare un percorso sicuro. In questo caso, l'indice `inizio` viene aggiornato a `medio + 1`.
- **Aggiornamento dell'intervallo**: Se è presente un ostacolo nella posizione media (cioè se `forestaGioco.getMappa()[medio][0]` è vero), viene aggiornato l'indice `fine` a `medio`. Questo indica che il percorso più sicuro si trova prima della posizione media.
- **Ripetizione del ciclo**: Il ciclo continua fino a quando l'intervallo è ridotto a un singolo punto, indicando che è stata individuata la posizione più sicura lungo l'asse Y.
- **Restituzione dell'indice finale**: Una volta che l'intervallo è ridotto a un singolo punto, l'indice `inizio` contiene l'indice della posizione più sicura lungo l'asse Y. Questo indice viene quindi restituito come risultato del metodo.

# Test degli Endpoint con Postman
Di seguito sono riportati esempi di come utilizzare Postman per testare gli endpoint:

- **Inizia un Nuovo Gioco**
  - Metodo: POST
  - URL: `http://localhost:8080/gioco/inizia`
  - Parametri: `dimensioneX=10`, `dimensioneY=10`

- **Attraversa la Foresta**
  - Metodo: PATCH
  - URL: `http://localhost:8080/gioco/attraversa`
  - Parametri: `giocoId=1`

# Divertiti ad Esplorare la Foresta dei Cicli!
Preparati per un'avventura emozionante nella Foresta dei Cicli! Usa i cicli e l'algoritmo di ricerca binaria per superare le sfide e attraversare la foresta con successo. Buon divertimento! 🌲🔍🎮
