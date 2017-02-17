Détails sur Let's Encrypt
=========================

Certificats de 90 jours, renouvellement suggéré à partir de 30 jours avant la
fin de vie.
Une durée de vie de 90 jours pousse à l'automatisation et permet de limiter les
dégats en cas de vol ou compromission de clé.

Algos :
-------

clés RSA de 2048 à 4096 bits de long
clés ECDSA P-256 et P-384

Limites de l'API :
------------------

Source : https://letsencrypt.org/docs/rate-limits/

* 20 certificats par semaine par domaine "principal" (*Certificates per
  Registered Domain*).
  Exemples :
  * *www.example.com* a pour domaine principal *example.com*
  * *new.blog.example.co.uk* a pour domaine principal *example.co.uk*
  (https://publicsuffix.org est utilisé determiner le domaine principal)
  Exception pour les renouvellements (*Renewal Exemption*)
* 100 FQDN "sous-domaine" par certificat (*Names per Certificate*).
  Exemple : SAN/UCC *example.com*, *pre-prod.example.com*, *static.example.com*,
  *blog.example.com*, etc.
* 5 certificats doublons par semaine (*Duplicate Certificate*).
  Exact = même domaines
  Pas d'exception pour les renouvellements : Donc faire attention à ne pas
  atteindre cette limite.
* 20 requêtes par seconde (*Overall Request Per Second*) sur `/new-reg`,
  `/new-authz` et `/new-cert`.
* 2000 requêtes par seconde sur le reste
* 500 enregistrements par adresse IP par 3 heures
* 300 autorisations en attente par compte
