# IFTOP-original-convertis-pour-Windows-

Tutoriel d’installation et d’utilisation de iftop pour Windows (avec Npcap)

Crédit : AVHIRAL 2025 (c)

Ce guide permet d’avoir iftop fonctionnel sur Windows (PowerShell / CMD) avec affichage du trafic, en passant par Npcap.

1) Installer Npcap (obligatoire)

Télécharge et lance Npcap (ex: npcap-1.85.exe).

Installez-le normalement.

(Optionnel mais recommandé) Redémarre Windows après installation.

2) Activer Npcap sur votre carte Ethernet

Si iftop --list ne montre que des “WAN Miniport”, c’est que Npcap n’est pas attaché à votre carte réseau.

Ouvrez les connexions réseau :

Win + R → tape ncpa.cpl → Entrée

Clic droit sur Ethernet (votre carte active) → Propriétés

Dans la liste, cochez :

Npcap Packet Driver (NPF) (ou intitulé proche)

Cliquez OK

Désactivez / Réactivez la carte Ethernet (ou redémarre)

3) Vérifier les interfaces visibles par iftop

Ouvrez PowerShell (idéalement en admin) et tapez :

iftop --list


Vous devez voir apparaître au moins une interface “Ethernet / Realtek / Intel / ASIX / Wi-Fi”, pas uniquement des miniports.

4) Lancer iftop sur la bonne interface (par index)

Quand iftop --list vous donne une liste numérotée, choisis l’index correspondant à votre carte réseau.

Exemple (si l’interface est [4]) :

iftop -i 4

5) Si tu ne voyez toujours “rien”

Assurez-vous de choisir la carte physique Ethernet/Wi-Fi, pas un “WAN Miniport”.

Génère du trafic (ouvrir un site web, lancer un téléchargement, ping).

Vérifiez que vous êtes bien connecté via cette interface (Ethernet vs Wi-Fi).

Donation (PayPal)

Si vous voulez soutenir : https://www.paypal.com/donate/?hosted_button_id=FSX7RHUT4BDRY
