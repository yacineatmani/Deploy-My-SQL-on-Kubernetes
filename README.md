# Deploy-My-SQL-on-Kubernetes
Voici les étapes pour déployer MySQL sur Kubernetes :

Créer un Secret Kubernetes :

Stocke le mot de passe root de MySQL de manière sécurisée.


Créer un PersistentVolumeClaim (PVC) :

Assure le stockage persistant pour les données MySQL.


Créer un Deployment :

Définit le conteneur MySQL et ses configurations.
Utilise le Secret pour le mot de passe.
Monte le volume persistant.


Créer un Service :

Expose MySQL à l'intérieur du cluster.


Appliquer la configuration :

Sauvegardez le YAML ci-dessus dans un fichier (par exemple mysql-deployment.yaml).
Appliquez-le avec la commande : kubectl apply -f mysql-deployment.yaml



Points importants :

Assurez-vous que votre cluster Kubernetes supporte les PersistentVolumes.
Ajustez la taille du stockage et la version de MySQL selon vos besoins.
Le mot de passe root dans le Secret est encodé en base64. Changez-le pour la production.

Pour vérifier le déploiement :

Vérifiez le pod : kubectl get pods
Vérifiez le service : kubectl get services
Vérifiez le PVC : kubectl get pvc

Pour vous connecter à MySQL :

Trouvez le nom du pod : kubectl get pods
Connectez-vous : kubectl exec -it [nom-du-pod] -- mysql -uroot -p
