# comunitasolidaliengine
 motore di ricerca marketplace tra comunità solidali
v.0
Questo motore permetterà a tutti i marketplace che utilizzano monete Alternative di poter comunicare i propri dati base utenti/articoli/monete in un motore di ricerca centralizzato
Tramite un protocollo HTTP JSON sarà possibile per tutti allargare il mercato di utenti. Per ogni articolo sarà esposta anche la moneta accettata dal commerciante, come procurarsela per chi non ce l'ha 
e come iscriversi alla comunità/market place  in cui opera il negoziante che vende un articolo scelto dall'utente tramite motore di riceca

API HTTP ( ? dominio non disponibile in fase di sviluppo solo per uso interno)

le prime api disponibile sono:
https://?//comunitasolidaliengine/Marketplace/NuovoArticolo
Header:
Content-type text/plain
accept */*
Connection keep-alive
nel body va passato una stringa formattata json (esempio):
{ "Auth":"????" , "Comunita": "proitaly" , "Codarticolo" : "ABCD123", "Moneta" : "val" ,   
   "Descrizionesintetica": "articolo test" , "Descrizionecompleta": "" , "Immaginelink":"https://m.media-amazon.com/images/I/81HPNejWmDL.__AC_SX300_SY300_QL70_ML2_.jpg", 
   "Prezzoeuro" : 10, "Prezzovaluta" : 10, "Linkarticolonegozio" : "" , "Linkiscrizionecomunita": "", "Linkinfomoneta":"", "categoria": "fai da te", "disponibilita": 2 }

in risposta se tutto ok si ottiene
status 200 OK
header:
Content-Type; application/json
Body:
{"codarticolo":"ABCD123","descrizionesintetica":"articolo test"","moneta":"val","valoreunitario":"10","qtadisp":"2"}
altrimenti codice di errore

https://?//comunitasolidaliengine/Marketplace/Nuovoutente
Header:
Content-type text/plain
accept */*
Connection keep-alive

nel body va passato una stringa formattata json (esempio):
{"Auth":"xxxxx" , "Comunita":"proitaly" , "Moneta": "val", "Username": "pippo", "Cognome" : "pluto", "Citta":"milano" , "Prov": "MI", "Regione": "lombardia" ,"Cap" : "20100", "Nazione": "Italy" , "email": "admin@dinastycoin.com"}
in risposta si ottiene
status 200 OK
header:
Content-Type; application/json

nel body:
{
    "Username": "pippo",
    "Nome": "",
    "Cognome": "pluto",
    "Citta": "milano",
    "Nazione": "Italy",
    "Cap": "20100",
    "Comunita": "proitaly",
    "Email": "",
    "Moneta": "val"
}