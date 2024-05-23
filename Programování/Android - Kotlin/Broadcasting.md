# Broadcasting
Po odeslání broadcastu se pošle daný Intent všem
BroadcastReceiverům zaregistrovaným na danou akci v
Intentu. Je potřeba implementovat pouze metodu
`onReceive( )`. Životní cyklus vázaný na danou komponentu. Jinak skončí po přijetí zprávy (`dokončení onReceive( )`).