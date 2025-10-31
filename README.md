# Déploiement d'une VM Ubuntu sur Azure avec Terraform

Ce projet permet de déployer une machine virtuelle Ubuntu sur Microsoft Azure, incluant le réseau, le stockage, la sécurité et la génération de clé SSH.

## Prérequis

- [Terraform](https://www.terraform.io/downloads.html)
- Un compte Azure avec les droits suffisants
- [Azure CLI](https://docs.microsoft.com/fr-fr/cli/azure/install-azure-cli) (pour l'authentification)

## Initialisation

1. **Authentification Azure**
   ```sh
   az login
   ```

2. **Initialiser Terraform**
   ```sh
   terraform init
   ```

3. **Vérifier le plan d'exécution**
   ```sh
   terraform plan
   ```

4. **Appliquer la configuration**
   ```sh
   terraform apply
   ```
   Confirme avec `yes` si demandé.

## Variables

Définis les variables nécessaires dans un fichier `terraform.tfvars` ou via l'environnement :
- `username` : nom d'utilisateur admin pour la VM

Exemple :
```hcl
username = "azureuser"
```

## Fichiers principaux

- `main.tf` : ressources principales (réseau, VM, stockage, sécurité)
- `variables.tf` : variables d'entrée
- `providers.tf` : configuration des providers Azure et Random
- `outputs.tf` : sorties utiles (IP, nom VM, etc.)

## Nettoyage

Pour supprimer l'infrastructure :
```sh
terraform destroy
```

---

Pour toute question, consulte la documentation officielle Terraform ou Azure.