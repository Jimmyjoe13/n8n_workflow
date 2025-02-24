# Email Analyse Bot

## Description
Ce workflow n8n est conçu pour analyser automatiquement les emails dans Gmail et détecter/supprimer les spams. Il utilise l'intelligence artificielle (Groq LLM) pour analyser le contenu des emails et prendre des décisions concernant leur légitimité.

## Fonctionnalités
- Récupération automatique des emails Gmail (incluant les spams)
- Analyse intelligente du contenu des emails via IA
- Suppression automatique des spams confirmés
- Gestion de la mémoire des conversations pour un meilleur contexte

## Composants du Workflow
1. **Déclencheur** : Manuel (When clicking 'Test workflow')
2. **Récupération des emails** : Node Gmail_get
3. **Traitement des données** : Node Edit Fields
4. **Analyse IA** :
   - AI Agent (LangChain)
   - Groq Chat Model (llama-3.3-70b-versatile)
   - Window Buffer Memory
5. **Action** : Gmail_delete pour la suppression des spams

## Configuration Requise
- Compte Gmail configuré avec OAuth2
- Compte Groq API pour l'accès au modèle LLM
- n8n version compatible avec les nodes LangChain

## Installation
1. Importer le fichier `email_analyse_bot.json` dans votre instance n8n
2. Configurer les credentials :
   - Gmail OAuth2
   - Groq API
3. Activer le workflow

## Utilisation
1. Lancer le workflow manuellement via le bouton "Test workflow"
2. Le bot analysera automatiquement les emails dans Gmail
3. Les spams identifiés seront supprimés automatiquement

## Paramètres d'Analyse
L'agent IA est configuré pour :
- Travailler en français
- Analyser le contenu des emails (snippet)
- Vérifier les labels
- Examiner l'expéditeur
- Évaluer l'objet du mail

## Sécurité
- Utilise l'authentification OAuth2 pour Gmail
- Stockage sécurisé des credentials dans n8n
- Analyse locale des emails via l'API Gmail

## Support
Pour toute question ou problème, veuillez créer une issue dans le repository du projet.

## Note
Ce workflow est configuré pour fonctionner avec les spams Gmail. Assurez-vous de bien vérifier les paramètres avant de l'activer en production.