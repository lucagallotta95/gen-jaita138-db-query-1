
/*Recupera tutti gli utenti registrati nel sistema.*/

SELECT *
FROM Utenti;


/* Recupera il nome, cognome e email di tutti gli utenti iscritti dopo il 1° marzo 2024.*/

SELECT nome, cognome, email
FROM Utenti
WHERE data_iscrizione > "01-03-2024";

  

/*Recupera tutti gli articoli insieme al nome e cognome dell'autore.*/

SELECT a.*,u.nome, u.cognome
FROM utenti u
JOIN articoli a ON u.id_utente =a.id_utente;

  
/*Recupera i titoli degli articoli pubblicati nel mese di maggio 2024.*/

SELECT a.titolo, a.data_pubblicazione
FROM articoli a
WHERE year(a.data_pubblicazione) = 2024 AND month(a.data_pubblicazione)= 5;


/*Recupera le prime 5 categorie ordinate alfabeticamente per nome.*/

SELECT *
FROM categorie c
ORDER BY c.nome_categoria
LIMIT 5;

/*Recupera gli articoli che appartengono alla categoria 'Tecnologia'.*/

  
SELECT *
FROM articoli a
JOIN articoli_categorie ac ON a.id_articolo = ac.id_articolo
JOIN categorie c ON ac.id_categoria =c.id_categoria
WHERE c.nome_categoria LIKE "Tecnologia";

  
/*Recupera le email degli utenti che hanno scritto almeno un articolo.*/

  
SELECT u.email
FROM utenti u
JOIN articoli a ON u.id_utente = a.id_utente ;

  
/*Recupera tutti gli articoli pubblicati tra il 1° giugno 2024 e il 31 agosto 2024.*/

SELECT a.*
FROM articoli a
WHERE a.data_pubblicazione
BETWEEN "2024-06-01" AND "2024-08-31";

  

/*Recupera i dettagli delle categorie associate all'articolo con `id_articolo` = 10.*/

SELECT c.*
FROM categorie c
JOIN articoli_categorie ac ON ac.id_categoria =c.id_categoria
WHERE ac.id_articolo = 10;

  

/*Recupera i nomi degli utenti ordinati per data di iscrizione più recente.*/

SELECT u.nome,u.data_iscrizione
FROM utenti u
ORDER BY u.data_iscrizione DESC;