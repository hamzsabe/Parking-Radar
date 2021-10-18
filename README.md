# Parking-Radar
Pour aider aux manœuvres, on trouve de plus en plus d’appareils d’assistance appelés radar de recul. On propose d’en étudier un, réalisé à base de CPLD dont le contenu sera programmé en exploitant le langage Verilog. L'appareil génére un son, image de la distance entre notre appareil et un objet ou obstacle. Ce son devient de plus en plus aigu au fur et à mesure que l’on se rapproche.


![US](https://user-images.githubusercontent.com/71197125/137821730-2dea8890-7f1e-47d4-8d5d-42df353e2ec7.jpg)


Pour cela, on utilisera les ultrasons. Le principe est simple, on émet une impulsion très courte à l’aide d’un transducteur ultrasonique et on récupère son écho (le signal impulsionnel réfléchi par un objet). On récupère à l’entrée de notre appareil les 2 signaux (Emit et Recept) porteurs d’impulsions décalées dans le temps. Emit est l’impulsion de départ et Recept représente son écho par l’objet.

La vitesse de propagation des sons est d’environ 300m/s dans l’air. L’écart de temps entre Emit et Recept dépend de la distance. L’onde faisant un aller et retour entre notre véhicule et l’obstacle. On a par exemple pour une distance de 5 cm un retard de 333 µs ou pour 50 cm de 3333 µs.

Notre appareil devra générer dans un haut-parleur (HP), un son de fréquence dépendante de cette durée. La fréquence sera dans la gamme des fréquences audibles.

On envoie une impulsion chaque 2/10 de seconde (cette information n’intervient pas sur notre étude). Le dispositif de génération des impulsions et de mise en forme de la réception n’est pas l’objet du projet.

![Radar1](https://user-images.githubusercontent.com/71197125/137821822-1ed29305-9460-4ca5-b329-a3acad54f0fd.jpg)

Remarques :

à gauche, un obstacle est plus proche de notre radar que sur la partie droite (dT1 est plus petit que dT2). Le signal généré devra donc être plus aigu à gauche,
on dispose, en plus des 2 signaux, d’une horloge de fréquence 1MHz.
La compréhension complète de la présentation n’est pas nécessaire à la réalisation du programme. Les explications qui suivent peuvent à elles seules suffire pour réaliser la tâche.

Le dispositif doit être opérationnel à partir d’un mètre jusqu’au contact. Si dT dépasse 6666, le haut parleur n’est pas piloté. La fréquence générée sera inversement proportionnelle à la distance (la période sera donc proportionnelle).

On demande d’imaginer un dispositif qui génère un signal de période proportionnelle à la distance, qui soit tel que l’on ait 3kHz sur le haut-parleur pour 333µs (dT = 333).
