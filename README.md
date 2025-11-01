# 🚀 Initiation à Kubernetes (K8S) : Labo Codespaces & Minikube

Bienvenue dans ce cours pratique d'introduction à **Kubernetes (K8S)** !

Pour vous permettre de vous concentrer sur les concepts clés sans perdre de temps avec l'installation, nous allons utiliser **GitHub Codespaces** et **Minikube**. Cet environnement vous offre un cluster K8S à nœud unique, prêt à l'emploi.

---

## 🛠️ Étape 1 : Forker le dépot

* Rendez-vous sur la page principale de ce dépôt GitHub.
* Cliquez sur le bouton **`Fork`** (en haut à droite de la page).
* Créez le *Fork* sur votre propre compte GitHub. Vous serez redirigé vers votre nouvelle copie du dépôt.

---
      
## 🏄 Étape 2 :  Démarrer l'environnement Codespaces

* Une fois sur la page de votre **dépôt forké**, cliquez sur le bouton **`< > Code`**.
* Sélectionnez l'onglet **`Codespaces`**.
* Cliquez sur **`Create codespace on main`** (ou créez un nouveau Codespace).
* GitHub va provisionner l'environnement. Le processus peut prendre quelques minutes.
* Une fois lancé, vous verrez l'interface **VS Code** dans votre navigateur, avec un terminal prêt à être utilisé.

---

## 🌟 Étape 3 : Démarrer Minikube

**Minikube** est un outil qui exécute un cluster Kubernetes à nœud unique *localement*. Dans Codespaces, Minikube utilise le **driver `docker`** pour créer le nœud K8S en tant que conteneur Docker.


Dans le terminal de votre Codespace, exécutez la commande suivante :

```bash
minikube start --driver=docker
```

**Surveillez le processus :**
* Minikube va télécharger les images nécessaires et démarrer les composants du plan de contrôle Kubernetes.
* Attendez que le message final de succès s'affiche. Il doit se terminer par :
    
 Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default.
    
        
**Vérifier l'état de Minikube :**

```bash
minikube status
```
**Résultat attendu :**
Les champs `host`, `kubelet` et `apiserver` devraient tous être à l'état `Running`.

---

## ✅ Étape 4 : Vérifier l'état du cluster  Kubernetes

Une fois Minikube démarré, vous utiliserez l'outil **`kubectl`** pour interagir avec le cluster.
```bash
kubectl get nodes
```

**Résultat attendu :** Vous devriez voir un seul nœud (nommé généralement `minikube`) avec l'état **`Ready`**.
        
NAME       STATUS   ROLES           AGE   VERSION

minikube   Ready    control-plane   2m    v1.33.1 

**Votre environnement est prêt ! Vous pouvez commencer à explorer les concepts de Kubernetes.**


## 🧹 Commandes Utiles (Après le cours)

Pour arrêter ou nettoyer votre environnement :

| Action | Commande | Description |
| :--- | :--- | :--- |
| **Arrêter Minikube** | `minikube stop` | Arrête le cluster, mais conserve les données. |
| **Supprimer Minikube** | `minikube delete` | Supprime complètement le cluster et toutes les données. |
