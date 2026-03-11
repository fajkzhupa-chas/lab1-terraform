# Lab 1 - Terraform & GCP

## Vad projektet gör
Detta projekt använder Terraform för att automatiskt provisionera en Ubuntu Linux VM i Google Cloud Platform (GCP). Det sätter också upp en automatisk backup-policy (snapshot) som körs dagligen.

## Hur man kör koden
För att deploya denna miljö, kör följande kommandon i terminalen:
1. `terraform init` (Laddar ner nödvändiga providers)
2. `terraform plan` (Visar vad som kommer att skapas)
3. `terraform apply` (Bygger infrastrukturen i GCP)

## Säkerhetsbeslut (Hardening)
I filen `startup.sh` har jag implementerat följande säkerhetsåtgärder:
* **UFW (Uncomplicated Firewall):** Blockerar all inkommande trafik som standard, förutom port 22 (SSH) så att vi kan logga in på servern.
* **Fail2ban:** Övervakar inloggningsförsök och blockerar IP-adresser tillfälligt om de skriver fel lösenord för många gånger (skyddar mot brute-force attacker).
* **Unattended-upgrades:** Ser till att servern automatiskt laddar ner och installerar viktiga säkerhetsuppdateringar från Ubuntu, så att vi slipper patcha manuellt.

## Screenshots
*(Lägg in bilden på dina gröna GitHub Actions-checkar här)*
*(Lägg in bilden på din körande VM i GCP Console här)*
