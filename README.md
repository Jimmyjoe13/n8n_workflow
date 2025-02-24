# Email Analysis Bot

## Description
Ce workflow n8n est conçu pour analyser automatiquement les emails dans Gmail, en se concentrant particulièrement sur la détection et la suppression des spams. Il utilise l'intelligence artificielle pour analyser le contenu des emails et prendre des décisions appropriées.

## Fonctionnalités
- Récupération automatique des emails Gmail (incluant les spams)
- Analyse intelligente du contenu des emails
- Suppression automatique des spams confirmés
- Gestion de la mémoire pour le contexte des conversations

## Architecture du Workflow

### Nodes principaux
1. **When clicking 'Test workflow'**
   - Point de départ manuel du workflow

2. **Gmail_get**
   - Récupère les 20 derniers emails (incluant les spams)
   - Utilise l'authentification OAuth2 Gmail

3. **Edit Fields**
   - Extrait et formate les informations importantes des emails :
     - Contenu (snippet)
     - Labels
     - Adresse de l'expéditeur
     - Sujet
     - ID de l'email

4. **AI Agent**
   - Analyse le contenu des emails
   - Système expert en français
   - Prend des décisions sur la nature spam/non-spam

5. **Gmail_delete**
   - Supprime les emails identifiés comme spam

6. **Window Buffer Memory**
   - Gère la mémoire temporaire pour le contexte des conversations

7. **Groq Chat Model**
   - Modèle LLM (llama-guard-3-8b) pour l'analyse

## Configuration Requise
- Compte n8n
- Compte Gmail avec accès OAuth2
- Accès à l'API Groq

## Installation
1. Importer le workflow dans n8n
2. Configurer les credentials Gmail
3. Configurer les credentials Groq
4. Activer le workflow

## Utilisation
1. Lancer le workflow manuellement via le trigger
2. Le système analyse automatiquement les emails
3. Les spams identifiés sont supprimés automatiquement

## Sécurité
- Utilise l'authentification OAuth2 pour Gmail
- Analyse sécurisée via Groq
- Gestion des sessions avec buffer de mémoire

## Maintenance
- Vérifier régulièrement les logs
- Ajuster les paramètres du modèle AI si nécessaire
- Maintenir à jour les credentials

## Support
Pour toute question ou problème, veuillez créer une issue dans le repository.