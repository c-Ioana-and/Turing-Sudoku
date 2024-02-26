# Implementare

Pentru implementarea acestui proiect am folosit reducerea de la K-Clique la SAT descrisă mai jos:

![](https://i.imgur.com/hlyDjn5.png)

Pentru reprezentarea internă a grafului am ales să folosesc matricea de adiacență, ținând cont de faptul că acesta este neorientat. 

Pentru a determina câte variabile voi folosi pentru SAT, am decis să mapez variabilele de tip x (indice: i, j) la x (indice: (i - 1) * n + j, unde n este numărul de noduri din graf, i este nodul care aparține clicii, iar j este un nod oarecare din graf. Așadar, ultima variabilă posibilă va fi x (indice: (k - 1) * n + n = k * n), deci voi avea în total k * n variabile.

Pentru a calcula numărul de clauze, există trei cazuri:
-	pentru a ne asigura că există al "i-lea" nod în clică, știm deja din enunț că sunt k clauze de acest fel;
-	pentru unicitatea nodurilor în clică, trebuie create (k * (k - 1) * n) / 2 clauze (i și j, nodurile din clică de comparat, trebuie să fie diferite și să nu se repete)
-	pentru fiecare 2 noduri care nu sunt conectate printr-o muchie, avem nevoie de k * (k - 1) * 2 clauze. Deci în total vor fi  nr_muchii_lipsă * k * (k - 1) * 2  clauze.

Makefile-ul conține doar o regulă de build care compilează sursa mea java și creează executabilul main, un script bash.
	


 
