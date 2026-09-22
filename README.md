# site-safaya

Pages statiques servies sur `safaya.io` : accueil, politique de confidentialite et CGU.

Ces deux dernieres sont referencees par l'ecran de consentement OAuth de Google
(Google Auth Platform > Branding), qui exige une page d'accueil et un lien de
confidentialite pour publier l'application en production.

## Structure

```
index.html                  accueil + mentions legales
style.css                   clair/sombre, responsive
confidentialite/index.html  politique RGPD
cgu/index.html              conditions d'utilisation
```

Les sous-dossiers donnent les URL `/confidentialite/` et `/cgu/` sans configuration
serveur particuliere.

## Avant mise en ligne

Les pages contiennent des encadres `todo` listant ce qui reste a completer :
raison sociale, adresse, numero d'immatriculation et adresse de contact.
Retirer ces encadres une fois les informations renseignees.

## Deploiement

Service **Static Site** dans Coolify, domaine `https://safaya.io`, publish directory `/`.
Le trafic passe par le tunnel Cloudflare `safaya-vps` puis Traefik : aucun changement DNS.

La racine `safaya.io` doit rester publique dans Cloudflare Access, sinon les liens
affiches sur l'ecran de consentement Google menent a un mur d'authentification.
