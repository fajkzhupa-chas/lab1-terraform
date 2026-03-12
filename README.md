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
<img width="1660" height="672" alt="Screenshot from 2026-03-11 13-31-33" src="https://github.com/user-attachments/assets/6280e96b-c711-4fb7-a843-644fb33f79c7" />
<img width="1086" height="481" alt="Screenshot from 2026-03-11 11-32-23" src="https://github.com/user-attachments/assets/40cfe0f1-8d6c-494f-bf83-9ba84e940042" />

