# COSTRUZIONE CASE
# RICEVITORE GNSS UNICORE UM982
Febbraio 2025

Un “lavoretto” abbastanza lungo iniziato ad aprile 2024, varie prove, varie soluzioni alla fine questo è il risultato in un case in alluminio 80 x 80 x 40 mm:
un ricevitore GNSS UNICORE UM982 che permette la connessione di 2 antenne GNSS, 2 schede Bluetooth HC05 (COM1 e COM2), un Datalog di backup automatico dei messaggi inviati alla porta COM, una batteria Lipo 3,7V 2500mAh con scheda di ricarica e unità di Step-Up a 5V che garantisce una autonomia di 4 ore con connessione USB esterna di  ricarica/supporto.
![00_img](https://github.com/user-attachments/assets/ce05509a-1b70-4159-917a-da2c9e5a6b14)

Come mai ho scelto di utilizzare questo tipo di scheda GNSS? 

https://en.unicore.com/products/dual-antenna-gnss-um982/

Innanzi a tutto il prezzo, un vero “Low-Cost” , ma anche la qualità e le caratteristiche veramente innovative. Devo dire che mi interessava scoprire cosa può fare un dispositivo GNSS dual-antenna, il cui utilizzo “principe” è nell’agricoltura di precisione con hardware e software di assistenza alla guida.
https://github.com/AgOpenGPS-Official/AgOpenGPS

Preciso subito per coloro che sono interessati alle sole funzioni topografiche, survey e mapping è consigliato l’altro modello singola antenna UM980 o il più sofisticato UM981 con IMU incorporata.

Si tratta comunque di dispositivi in grado di ricevere i segnali Galileo E6B e quindi accedere ai servizi Galileo HAS che permettono/permetteranno precisioni planimetriche inferiori ai 20 cm e precisioni altimetriche inferiori ai 40 cm. 

Il tutto dipenderà molto dal firmware presente nella scheda GNSS ed ai futuri sviluppi ed aggiornamenti.

Il servizio Galileo High Accuracy Service (HAS) fornisce  l'accesso gratuito , tramite il segnale Galileo (E6-B) e tramite mezzi terrestri (Internet), alle informazioni necessarie per stimare una soluzione di posizionamento accurata utilizzando un algoritmo di posizionamento preciso in tempo reale. 

https://www.gsc-europa.eu/galileo/services/galileo-high-accuracy-service-has
