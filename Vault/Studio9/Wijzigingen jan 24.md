DB prefix aangepast naar wpsnjpq_ om beter tegen hacks te beschermen. Er zouden nog kolommen in tabellen kunnen zijn die verwijzen naar wpstg0_ (de vorige prefix) of wp_ (de originele prefix lang geleden). Mochten er bepaalde dingen niet werken dan kan het wellicht helpen om in de database deze velden op te zoeken en de prefix daar te veranderen. Bijv in de wpsnjpq_usermeta tabel of de wpsnjpq_options tabel. Evt een google search voor 'wordpress change table prefix' doen om te kijken in welke tabellen nog meer waardes zouden kunnen staan die verwijzen naar de oude prefix.