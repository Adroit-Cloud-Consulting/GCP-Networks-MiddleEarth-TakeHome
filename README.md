# 🏰 Middle-earth Infrastructure Challenge

Welcome, Architect of the Free Peoples.

The Fellowship is migrating its operations from the Misty Mountains (on-prem) to the cloud. Your task is to build the foundational GCP infrastructure that will securely host Middle-earth’s new platform, **Palantír**. This includes secure network design, access controls via Cloud Armor, and reproducible infrastructure-as-code using Terraform.

The Council of Elrond expects a production-ready approach, not a wizard’s guesswork.

---

## 🧙‍♂️ Scenario

### Organisation: **Middle-earth Operations (MEO)**

**Mission:** A secure communication and coordination platform for rangers, elves, and dwarves across multiple realms.

**Codename:** `Palantír`

The platform must:

- Be securely accessible only by known allied regions.
- Be deployed using infrastructure-as-code (Terraform).
- Defend against hostile traffic from Sauron’s forces.

---

## 🛠️ Your Task

Using **Google Cloud Platform** and **Terraform**, build the following:

### 1. VPC Network

- Create a custom-mode VPC: `middleearth-net`
- Add two subnets in different regions:
  - `gondor-frontend`: for hosting the public frontend (e.g. GKE or managed instance group)
  - `rohan-backend`: for backend services with **no external IPs**
- Ensure proper firewall rules between frontend and backend
- Backend should only be accessible internally

### 2. HTTPS Load Balancer

- Global external HTTPS load balancer in front of the frontend service
- Use a managed SSL certificate

### 3. Cloud Armor Policy

- Name: `gate-of-minas-tirith`
- Restrict access to UK IP ranges and "The Shire" (you define the IPs)
- Block fake "Mordor" IP ranges (your choice)
- Apply OWASP WAF rules to block common threats

### 4. Terraform Code Structure

- Use modules to keep the code clean and reusable
- Use input variables and sensible outputs
- Avoid hardcoding values like project ID or secrets

### 5. (Bonus) Monitoring & CI/CD

Optional but appreciated:

- Set up basic monitoring and logging using GCP Operations Suite
- Add a CI/CD pipeline (e.g. GitHub Actions or Cloud Build) to lint/validate your Terraform

---

## 📦 Deliverables

- A GitHub repo (or zipped folder) with:
  - Your complete Terraform code
  - A short **README** (max 1 page) explaining your setup, structure, and any assumptions
  - A screenshot of the deployed infrastructure in the GCP Console (please sanitise)

---

## 🎤 Follow-Up Session

You'll have a short session (30–45 mins) with one of our engineers where you’ll:

- Walk through your architecture and Terraform code
- Explain your Cloud Armor policy and how you tested it
- Talk us through your network layout and reasoning
- Discuss any compromises or decisions you made

We’re looking for clarity of thought, practical skill, and awareness of production realities.

---

## ⚠️ A Note on AI and Assistance

This is a practical test based on real-world experience. We expect your own work.

AI-generated code or heavily assisted solutions are easy to spot, and they won’t get past the walkthrough.

---

May your configs be clean and your policies strict.
— The Council of Elrond
