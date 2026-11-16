# TP 0 — Application de conversation avec JSF et CDI

> Projet réalisé par Othmane ABIDI dans le cadre du TP 0.

## 🛠️ Outils et technologies

| Outil / Technologie | Utilisation dans le projet |
|---|---|
| ☕ Java | Développement de la logique applicative |
| 🌐 JSF / Facelets | Construction de l’interface et gestion du formulaire |
| 💉 CDI | Gestion des composants et de leurs dépendances |
| 📝 HTML / XHTML | Structure de la page et affichage de la conversation |
| 🐟 Payara Server | Serveur d’applications utilisé pour déployer et exécuter le projet |
| 📦 Maven | Gestion du projet et de sa construction |
| 🌿 Git | Suivi des modifications et gestion des versions |
| 🐙 GitHub | Hébergement du dépôt et partage du code source |

## 🎯 Contexte

Ce projet constitue une première mise en pratique du développement d’une application web Java utilisant JSF et CDI, déployée sur Payara Server.

L’application propose une interface de conversation permettant de saisir une question, de sélectionner un rôle et d’afficher une réponse produite par le traitement de l’application.

Cette version constitue une base fonctionnelle destinée à être enrichie ultérieurement par un traitement personnel.

## ❓ Problématique

Comment réaliser une interface de conversation qui permette de :

- récupérer les informations saisies dans un formulaire ;
- vérifier les champs obligatoires ;
- déclencher un traitement côté serveur ;
- afficher les échanges en conservant leur historique ;
- réinitialiser la conversation pour commencer un nouveau chat ?

Le projet permet également d’observer la différence entre le code source JSF et le HTML effectivement reçu par le navigateur.

## ⚙️ Réalisation

### Interface de conversation

L’interface permet à l’utilisateur de :

1. sélectionner un rôle ;
2. saisir une question ;
3. envoyer le formulaire ;
4. consulter la réponse et les échanges précédents ;
5. commencer une nouvelle conversation avec le bouton « Nouveau chat ».

### Organisation du code

- `index.xhtml` : interface de conversation et formulaire ;
- `Bb.java` : gestion des interactions entre la page et le traitement ;
- `GenerateurReponse.java` : traitement chargé de produire la réponse.

### Validation et tests réalisés

| Scénario testé | Résultat |
|---|---|
| Envoyer une question avec un rôle sélectionné | Validé |
| Enchaîner plusieurs échanges | Historique conservé |
| Cliquer sur « Nouveau chat » | Conversation réinitialisée |
| Envoyer une question vide | Message de validation affiché |
| Envoyer sans sélectionner de rôle | Message de validation affiché |

### Contrôle du HTML généré

La consultation du code source de la page a permis de vérifier que :

- la balise JSF `<h:inputTextarea>` n’apparaît plus ;
- les expressions `#{bb...}` n’apparaissent plus ;
- la balise HTML `<textarea>` est présente.

Ce contrôle illustre la transformation de la vue JSF en HTML avant son affichage dans le navigateur.

## 📚 Leçons retenues

Ce TP m’a permis de mieux comprendre :

- la liaison entre les composants d’une page JSF et un bean Java ;
- la séparation entre l’interface, la gestion des interactions et le traitement de la réponse ;
- l’importance de la validation des données saisies ;
- la gestion de l’historique d’une conversation et de sa réinitialisation ;
- la différence entre une vue JSF et le HTML généré ;
- le déploiement et l’exécution de l’application sur Payara Server ;
- l’utilisation de Git et GitHub pour conserver et partager une version fonctionnelle du projet.

Une étape importante a été de tester les cas d’erreur, et pas uniquement le fonctionnement normal du formulaire.

## 🚧 Évolution prévue : bonus personnel

Le traitement personnel n’est pas encore implémenté.

La piste envisagée concerne la sécurité opérationnelle : un pré-triage simplifié de journaux de sécurité, inspiré des activités d’un SOC.

L’objectif serait de reconnaître quelques mots-clés dans une ligne de journal et de retourner une catégorie accompagnée d’une piste de vérification.

Ce futur traitement reposerait sur des règles simples. Il ne constituerait ni une analyse complète de sécurité ni une confirmation automatique d’attaque.

## 👤 Auteur

Othmane ABIDI

Dépôt du projet : https://github.com/othmane71-art/tp0IA
