Microservizi principali
User Service

Descrizione: Gestisce la registrazione, autenticazione e gestione dei profili utenti (host e clienti).
Tecnologie: Spring Boot + MySQL.
Endpoint principali:
POST /register: Registrazione di un nuovo utente (host o cliente).
POST /login: Autenticazione e generazione token JWT.
GET /profile/{userId}: Recupero dei dettagli del profilo utente.
PUT /profile/{userId}: Aggiornamento del profilo utente.
Database:
Tabelle per utenti, ruoli (host/cliente), e sessioni utente.
Listing Service

Descrizione: Gestisce la creazione, modifica e visualizzazione degli annunci da parte degli host.
Tecnologie: Spring Boot + MySQL.
Endpoint principali:
POST /listings: Creazione di un nuovo annuncio.
GET /listings: Recupero di tutti gli annunci (con filtri).
GET /listings/{listingId}: Recupero dei dettagli di un annuncio specifico.
PUT /listings/{listingId}: Aggiornamento di un annuncio esistente.
DELETE /listings/{listingId}: Cancellazione di un annuncio.
Database:
Tabelle per annunci, categorie, servizi, e immagini associate agli annunci.
Booking Service

Descrizione: Gestisce le prenotazioni e il loro stato (prenotata, confermata, annullata).
Tecnologie: Spring Boot + MySQL.
Endpoint principali:
POST /bookings: Creazione di una nuova prenotazione.
GET /bookings/{userId}: Recupero delle prenotazioni di un utente (host o cliente).
PUT /bookings/{bookingId}: Conferma o annullamento di una prenotazione.
Database:
Tabelle per le prenotazioni, stato delle prenotazioni, e storico.
Chat Service

Descrizione: Gestisce la comunicazione tra host e clienti con chat in tempo reale.
Tecnologie: Spring Boot + WebSocket (Spring Boot WebSocket).
Endpoint principali:
GET /chat/rooms/{roomId}: Recupero dei messaggi in una stanza di chat.
POST /chat/rooms/{roomId}/messages: Invia un messaggio in una stanza di chat.
Database:
Tabelle per stanze di chat e messaggi.
Notification Service

Descrizione: Invia notifiche in tempo reale ai clienti e agli host (es. prenotazioni confermate, messaggi ricevuti).
Tecnologie: Spring Boot + Firebase Cloud Messaging (FCM) o un sistema di messaggistica come Apache Kafka.
Funzionalità:
Notifiche push via FCM.
Sistema di code (es. Kafka) per la gestione delle notifiche asincrone.
2. Frontend (Angular)
Il frontend sarà una Single Page Application (SPA) sviluppata con Angular. Il progetto sarà organizzato per moduli, ciascuno dedicato a una parte specifica dell'applicazione.

Moduli principali:

Auth Module: Gestisce login, registrazione e autenticazione JWT.
Listings Module: Visualizzazione e gestione degli annunci. Include:
Listings List Component: Vista per visualizzare tutti gli annunci disponibili con filtri.
Listing Details Component: Vista con i dettagli di un annuncio e opzioni di prenotazione.
Booking Module: Gestisce la visualizzazione e gestione delle prenotazioni per clienti e host.
Chat Module: Implementa la chat in tempo reale con il servizio WebSocket.
Profile Module: Gestisce la visualizzazione e modifica del profilo utente (cliente e host).
Servizi Angular:

Auth Service: Per autenticazione e gestione token.
Listings Service: Comunicazione con il Listing Service backend.
Booking Service: Comunicazione con il Booking Service backend.
Chat Service: Connessione e gestione delle stanze di chat in tempo reale tramite WebSocket.
Notification Service: Integrazione con FCM o un sistema di notifiche per aggiornamenti in tempo reale.