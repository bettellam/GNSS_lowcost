# COSTRUZIONE CASE
# RICEVITORE GNSS UNICORE UM982
Febbraio 2025

Un “lavoretto” abbastanza lungo iniziato ad aprile 2024, varie prove, varie soluzioni alla fine questo è il risultato in un case in alluminio 80 x 80 x 40 mm:
un ricevitore GNSS UNICORE UM982 che permette la connessione di 2 antenne GNSS, 2 schede Bluetooth HC05 (COM1 e COM2), un Datalog di backup automatico dei messaggi inviati alla porta COM, una batteria Lipo 3,7V 2500mAh con scheda di ricarica e unità di Step-Up a 5V che garantisce una autonomia di 4 ore con connessione USB esterna di  ricarica/supporto.
![00_img](./image/00_img.png)

Come mai ho scelto di utilizzare questo tipo di scheda GNSS? 

https://en.unicore.com/products/dual-antenna-gnss-um982/

Innanzi a tutto il prezzo, un vero “Low-Cost” , ma anche la qualità e le caratteristiche veramente innovative. Devo dire che mi interessava scoprire cosa può fare un dispositivo GNSS dual-antenna, il cui utilizzo “principe” è nell’agricoltura di precisione con hardware e software di assistenza alla guida.
https://github.com/AgOpenGPS-Official/AgOpenGPS

Preciso subito per coloro che sono interessati alle sole funzioni topografiche, survey e mapping è consigliato l’altro modello singola antenna UM980 o il più sofisticato UM981 con IMU incorporata.

Si tratta comunque di dispositivi in grado di ricevere i segnali Galileo E6B e quindi accedere ai servizi Galileo HAS che permettono/permetteranno precisioni planimetriche inferiori ai 20 cm e precisioni altimetriche inferiori ai 40 cm. 

Il tutto dipenderà molto dal firmware presente nella scheda GNSS ed ai futuri sviluppi ed aggiornamenti.

Il servizio Galileo High Accuracy Service (HAS) fornisce  l'accesso gratuito , tramite il segnale Galileo (E6-B) e tramite mezzi terrestri (Internet), alle informazioni necessarie per stimare una soluzione di posizionamento accurata utilizzando un algoritmo di posizionamento preciso in tempo reale. 

https://www.gsc-europa.eu/galileo/services/galileo-high-accuracy-service-has

Alcune immagini in fase di realizazione:

![01_img](./image/01_img.png)

Ho realizzato ulteriormente una “barra GNSS” dotata di 2 antenne che aggancio alla barra portatutto della mia autovettura per testare le prestazioni e precisioni in HEADING MODE:
---- immagine ------


Configurazione UM982:

<pre><i>$command,CONFIG,response: OK*54
$CONFIG,ANTENNA,CONFIG ANTENNA POWERON*7A
$CONFIG,NMEAVERSION,CONFIG NMEAVERSION V410*47
$CONFIG,RTK,CONFIG RTK TIMEOUT 600*69
$CONFIG,RTK,CONFIG RTK RELIABILITY 3 1*76
$CONFIG,PPP,CONFIG PPP TIMEOUT 120*6C
$CONFIG,PPP,CONFIG PPP ENABLE E6 HAS*01
$CONFIG,PPP,CONFIG PPP CONVERGE 10 15*20
$CONFIG,HEADING,CONFIG HEADING RELIABILITY 3*67
$CONFIG,HEADING,CONFIG HEADING FIXLENGTH*6F
$CONFIG,HEADING,CONFIG HEADING LENGTH 150.60 0.50*3F
$CONFIG,DGPS,CONFIG DGPS TIMEOUT 600*69
$CONFIG,RTCMB1CB2A,CONFIG RTCMB1CB2A ENABLE*25
$CONFIG,ANTENNADELTAHEN,CONFIG ANTENNADELTAHEN 0.0000 0.0000 0.0000*3A
$CONFIG,SBAS,CONFIG SBAS ENABLE EGNOS*55
$CONFIG,PPS,CONFIG PPS ENABLE GPS POSITIVE 500000 1000 0 0*6E
$CONFIG,SIGNALGROUP,CONFIG SIGNALGROUP 3 6*01
$CONFIG,ANTIJAM,CONFIG ANTIJAM AUTO*2B
$CONFIG,AGNSS,CONFIG AGNSS DISABLE*70
$CONFIG,BASEOBSFILTER,CONFIG BASEOBSFILTER DISABLE*70
$CONFIG,LOGSEQ,CONFIG LOGSEQ 1*15
$CONFIG,COM1,CONFIG COM1 115200*23
$CONFIG,COM2,CONFIG COM2 115200*23
$CONFIG,COM3,CONFIG COM3 115200*23
</i></pre>

<pre><i>$command,UNILOGLIST,response: OK*4A
#UNILOGLIST,92,GPS,FINE,2353,142915000,0,0,18,296;
23
GNGGA COM1 1 	  GNGGA COM2 1 	  GNGGA COM3 1
GPGSA COM1 1 	  GPGSA COM2 1 	    GPGSA COM3 1
GNGSV COM1 1 	  GNGSV COM2 1 	    GNGSV COM3 1
GNRMC COM1 1 	  GNRMC COM2 1 	    GNRMC COM3 1
GPVTG COM1 1 	  GPVTG COM2 1 	    GPVTG COM3 1
GPZDA COM1 1 	  GPZDA COM2 1 	    GPZDA COM3 1
GPGST COM1 1 	  GPGST COM2 1 	    GPGST COM3 1
AGRICA COM1 1 
PVTSLNA COM1 1  
</i></pre>

<pre><i>$command,versiona,response: OK*45
#VERSIONA,92,GPS,FINE,2353,143029000,0,0,18,746;"UM982","R4.10Build13495","HRPT00‑S10C‑P",
  "2310415000012‑LR23A1224506723","ff3bdb9914dca7db","2024/04/02"*68ebfbd8
</i></pre>

Per sperimentare l’utilizzo del ricevitore GNSS UM982 ho altresì sviluppato un’interfaccia in PyGis per la lettura dei messaggi satellitari ( tuttora in fase di sviluppo e test ) che potrebbe diventare in futuro un plugin di QGis o se riesco implementare il tutto nell’attuale interfaccia GNSS presente in QGis.  

![02_img](./image/02_img.png)

![03_img](./image/03_img.png)

Per chi volesse replicare il dispositivo , di seguito troverete l'elenco dei materiali utilizzati:

|Foto |Link  |
|---|---|
<img src="./image/01_um982.png"  width="400px"/>| [01_um982](https://it.aliexpress.com/item/1005006356627581.html ) |
|<img src="./image/02_dissipatori.png"  width="400px"/>| [02_dissipatori](https://it.aliexpress.com/item/4000348002518.html ) |
|<img src="./image/03_cavetti_antenne_gnss.png"  width="400px"/>| [03_cavetti_antenne_gnss](https://it.aliexpress.com/item/1005004620858652.html ) |
|<img src="./image/04_case_AL.png"  width="400px"/>| [04_case_AL](https://it.aliexpress.com/item/1005006828775169.html ) |
|<img src="./image/05_cavetti_x_bluetooth.png"  width="400px"/>| [05_cavetti_x_bluetooth](https://it.aliexpress.com/item/1005006389290211.html ) |
|<img src="./image/06_connettori_angolari_COM1_2_UM982.png"  width="400px"/>| [06_connettori_angolari_COM1_2_UM982](https://it.aliexpress.com/item/1005005288629414.html ) |
|<img src="./image/07_giunzione_bluetooth.png"  width="400px"/>| [07_giunzione_bluetooth](https://it.aliexpress.com/item/1005007617385129.html ) |
|<img src="./image/08_interruttore_bluetooh.png"  width="400px"/>| [08_interruttore_bluetooh](https://it.aliexpress.com/item/32966597068.html ) |
|<img src="./image/09_bluetooth_HC05.png"  width="400px"/>| [09_bluetooth_HC05](https://it.aliexpress.com/item/32817137671.html ) |
|<img src="./image/10_caricabatteria.png"  width="400px"/>| [10_caricabatteria](https://it.aliexpress.com/item/32798858483.html ) |
|<img src="./image/11_DC-DC_boster_step_up_alimentazione_UM982.png"  width="400px"/>| [11_DC-DC_boster_step_up_alimentazione_UM982](https://it.aliexpress.com/item/1005003203922131.html ) |
|<img src="./image/12_batteria_3.7V_2500mAh.png"  width="400px"/>| [12_batteria_3.7V_2500mAh](https://it.aliexpress.com/item/1005006745853422.html ) |
|<img src="./image/13_datalog.png"  width="400px"/>| [13_datalog](https://it.aliexpress.com/item/1005001351187842.html ) |
|<img src="./image/14_Micro_SD_32GB.png"  width="400px"/>| [14_Micro_SD_32GB](https://it.aliexpress.com/item/32691928032.html ) |
|<img src="./image/15_nastro_dielettrico.png"  width="400px"/>| [15_nastro_dielettrico](https://it.aliexpress.com/item/1005005058190496.html ) |
|<img src="./image/16_Connettore_Type-C_v1.png"  width="400px"/>| [16_Connettore_Type-C_v1](https://it.aliexpress.com/item/1005007148475800.html ) |
|<img src="./image/17_Connettore_Type-C_v2.png"  width="400px"/>| [17_Connettore_Type-C_v2](https://it.aliexpress.com/item/1005006477416745.html ) |
|<img src="./image/18_interrutore_generale.png"  width="400px"/>| [18_interrutore_generale](https://it.aliexpress.com/item/1005006495091965.html ) |
|<img src="./image/19_guida_luce_led.png"  width="400px"/>| [19_guida_luce_led](https://it.aliexpress.com/item/1005006150875834.html ) |
|<img src="./image/20_distanziatori.png"  width="400px"/>| [20_distanziatori](https://it.aliexpress.com/item/32862529967.html ) |
|<img src="./image/21_dadi_1-4.png"  width="400px"/>| [21_dadi_1-4](https://it.aliexpress.com/item/1005001917849687.html ) |
|<img src="./image/22_adattatore_5-8_1-4.png"  width="400px"/>| [22_adattatore_5-8_1-4](https://it.aliexpress.com/item/1005005936639212.html ) |
|<img src="./image/23_splitter_gnss.png"  width="400px"/>| [23_splitter_gnss](https://it.aliexpress.com/item/1005005753608505.html ) |
|<img src="./image/24_connettore_sma.png"  width="400px"/>| [24_connettore_sma](https://it.aliexpress.com/item/1005006603346164.html ) |
|<img src="./image/25_cavo_adattatore_usb.png"  width="400px"/>| [25_cavo_adattatore_usb](https://it.aliexpress.com/item/1005006203091645.html ) |
|<img src="./image/26_antenne_gnss.png"  width="100px"/>| [26_antenne_gnss](https://it.aliexpress.com/item/1005003069610289.html ) |
|<img src="./image/27_cavo_sma_3m.png"  width="400px"/>| [27_cavo_sma_3m](https://it.aliexpress.com/item/1005003069610289.html ) |
|<img src="./image/28_cavo_sma_5m.png"  width="400px"/>| [28_cavo_sma_5m](https://it.aliexpress.com/item/1005006413671801.html ) |
|<img src="./image/29_manicotto.png"  width="400px"/>| [29_manicotto](https://it.aliexpress.com/item/1005005088472531.html ) |
|<img src="./image/30_batteria.png"  width="400px"/>| [30_batteria](https://it.aliexpress.com/item/1005007293369749.html ) |
|<img src="./image/31_batteria.png"  width="400px"/>| [31_batteria](https://it.aliexpress.com/item/1005007520617163.html ) |
|<img src="./image/32_batteria.png"  width="400px"/>| [32_batteria](https://it.aliexpress.com/item/1005007586902014.html ) |
|<img src=""  width="400px"/>| [33_fascette](https://it.aliexpress.com/item/4001271678128.html ) |

