:package: CONSEGNA
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.

:rock: MILESTONE 1
Dopo aver creato il progetto ragionate sui componenti e cercate di ricalcare quanto visto nei live coding di oggi e venerdì.
Come dati utilizzate l'array in allegato. Potete incollarlo nel vostro data, oppure importare il file come visto oggi.
Avrete un componente padre (es. CardsList) che dichiara l'array nel data e vi cicla per passare il singolo dato al figlio (es. SingleCard) tramite le sue props.

:rock: MILESTONE 2
Spostate i dati in questione in uno store.js, all'interno di un array che chiamerete ad esempio carte.
Il componente padre (es. CardsList) richiama store.carte e vi cicla per passare il singolo dato al figlio (es. SingleCard).
Vi chiederete cosa cambia rispetto a prima? Cosa ci guadagno? Nulla! Ma ci tornerà utile per bonus con axios :wink:

:gift: BONUS
Recuperate questi dati tramite una chiamata axios da effettuare al mount dell'applicazione.
Per oggi possiamo importare axios tramite CDN, come al solito.
Questa chiamata andrà a scrivere su store.carte che quindi dovrà essere dichiarato come array vuoto nello store.js
L'api da richiamare si trova qui.

:gift: BONUS #2
L'indirizzo che vi ho fornito stampa solo le prime 10 carte. Se volessi visualizzare le prime 20 carte? Oppure le prime 20 carte a partire dalla 15esima? Guardate bene l'indirizzo e fate qualche prova :wink:
Qui trovate anche la documentazione delle API se volete capire bene quali dati aspettarvi.