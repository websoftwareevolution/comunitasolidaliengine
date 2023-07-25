# comunitasolidaliengine
 motore di ricerca marketplace tra comunità solidali
v.0
Questo motore permetterà a tutti i marketplace che utilizzano monete Alternative di poter comunicare i propri dati base utenti/articoli/monete in un motore di ricerca centralizzato
Tramite un protocollo HTTP JSON sarà possibile per tutti allargare il mercato di utenti. Per ogni articolo sarà esposta anche la moneta accettata dal commerciante, come procurarsela per chi non ce l'ha 
e come iscriversi alla comunità/market place  in cui opera il negoziante che vende un articolo scelto dall'utente tramite motore di riceca

API HTTP ( ? dominio non disponibile in fase di sviluppo solo per uso interno)

le prime api disponibili (dominio temporaneo durante la fase di sviluppo):
POST https://development.dinastycoin.club//comunitasolidaliengine/Marketplace/NuovoArticolo
Header:
Content-type text/plain
accept */*
Connection keep-alive
nel body va passato una stringa formattata json (esempio) (Codice Autorizzazione non ancora implementato):
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

POST https://development.dinastycoin.club//comunitasolidaliengine/Marketplace/Nuovoutente
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

 
POST: http://development.dinastycoin.club/comunitasolidaliengine/Marketplace/NuovoNegozio
body: { "Auth":"????" , "Comunita": "proitaly" , "Negozio" : "Panificio san carlo", "Moneta" : "val" ,   "Latitudine": "45,42051000" , "Longitudine": "10,99002000" , "Categoria":"alimentari", "Tag" : "pane, vino", "Nazione" : "italy", "Citta" : "Verona" , "Sitoweb": "https://panificiosancarlo.it", "Linkvetrina":"xxxxxxxx" }

in risposta si ottiene
status 200 OK
header:
Content-Type; application/json

nel body:
{
    "recorid": "4",
    "nomenegozio": "Panificio san carlo",
    "moneta": "val",
    "categoria": "alimentari",
    "comunita": "proitaly",
    "datareg": "25/07/2023"
}