# checkpoint_exo1 :

## 1.1 Éléments du réseau - QUIZZ :

1\ Pour le matériel B, connais-tu ses différences avec A ?
  * le matériel A est un switch (commutateur) , le B est un firewall (pare-feu) :
     - le commuateteur est un equipemnt qui fonctionne comme un pont multiports et qui permet de relier plusieurs segments d'un réseau informatique entre eux et de recopie des données reçues sur le seul portd estinataire en fonction de l'adresse MAC destinationn ,il fonctionne au niveau de la couche 2 du modèle OSI (couche de liaison de données).
    - pfsens est un pare-feu et un routeur qui offre la sécurité et la gestion du trafic reseau ,il permet d'interconnecter differents reseaux en utilisant divrs protocoles

2\ Que représente em0, em1, em2 ?
   * se sont des interfaces réseaux :
      - em0 : represente l'interface WAN
      - em1 : represente l'interface LAN
      - em1 : represente l'interface OPT1

3\ Que signifie /26 ?
   * /26 represente le masque de sous-reseau (les 26 premiers bits sont 1 et le reste sont a 0)

4\ Dans le vocabulaire IP, qu'est-ce que Ubuntu-1, Ubuntu-2, ... ?
   * ubuntu-1,ubuntu-2 sont des noms ( génériques et modifiables ) utilisés pour désigner les machines de notre reseau , dans notre cas les machines execute le system d'exploitation ubuntu .
     
5\ De même, qu'est-ce que A et B ?
   * A et B sont des equipements ou des éléments qui constitue notre reseau dans notre exemple A est un switch et B un firewall.

6\ Peut-on considérer que Ubuntu-2 est connecté directement à em1 de l'équipement pfSense ?      
   * non Ubuntu-2 nest pas directement connnecté a l'em1 de l'équipemnt pfSense .

## 1.2 Etude théorique :

11\ calcul pour les deux réseaux :
Ubuntu-1 : 10.0.1.1/26
- calcul de ladresse de diffusion : 
  * masque de sous-reseau : /26 en decimale : 255.255.255.192
    192 en binaire : 11000000
  * adresse ip : 10.0.1.1  les 8 derniers bites en binaire : 00000001
pour trouvrer ladresse de brodcast je 1 tou les bites de la partie machine : 00111111 (en décimal, cela donne 63)
 * Adresse de diffusion : 10.0.1.63
- la plage d'adresse disponible : Le nombre d’adresses disponibles à l’adressage se calcule comme suit : 2 puissance le nbre bits hôte – 2
  32-26=6    2^6=64-2=62
  * Il y a un total de 62 adresses disponibles pour les hôtes dans ce réseau 

Ubuntu-2 : 10.0.0.1/24
 - ladresse de diffusion : 10.0.0.255
 - La plage d'adresses disponible : 254

12\ La machine Ubutun-1 et Ubutun-2 peuvent elle communiquer entre elle ?
   * non , elles ne peuvent pas communiquer entre elles car elles ne sont pas dans le meme sous-reseau .

13\ De même, quelles machines vont pouvoir sortir du réseau ?
   * les deux machines ont des adresses privés donc elles ont besoin d'un routeur pour acceder a interent (sortir ) dans notre cas elles peuvent sortir grace a la présence du pfsense (firewall)

14 \  On veut passer les adresses IP des machines en dynamique pour qu'elles puissent toutes communiquer entre-elles. Doit-on ajouter des éléments au schéma pour que cela soit possible ?
 * situation 1 : ajouter un serveur DHCP
 * situation 2 : configurer manuellement chaque adresse IP sur chaque machine.
 



