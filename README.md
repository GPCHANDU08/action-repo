# GitHub Actions – CI/CD Demo Repository

![GitHub](https://img.shields.io/badge/GitHub-Actions-blue)
![Python](https://img.shields.io/badge/Python-3.x-success)
![Flask](https://img.shields.io/badge/Flask-Backend-orange)
![MongoDB](https://img.shields.io/badge/MongoDB-Local-green)
![Status](https://img.shields.io/badge/Project-Demo-lightgrey)

This repository is used to **simulate real GitHub events** (Push / Pull Request / Merge) that will be received and logged by the Flask webhook receiver hosted in the `webhook-repo`.

---

## 🎯 Purpose

This repo acts as a **dummy workload project**, where:

* Developers push updates
* Create branches
* Open Pull Requests
* Merge into the main branch

Every action triggers a **GitHub webhook** call that is captured by the Flask application running locally in `webhook-repo`.

This setup demonstrates:

* GitHub → Webhook Delivery
* Webhook Logging → MongoDB
* Real-time UI dashboard updates

---

## ⚙ Webhook Flow

```
action-repo  ➜  GitHub Webhook  ➜  Flask Receiver  ➜  MongoDB  ➜  Live UI
```

---

## 📁 Repository Contents

* Sample Python files / commits
* Dummy workflow triggers
* Small code changes for realistic testing

You can simulate:

### ✔ Push Event

```
git add .
git commit -m "Updated example code"
git push
```

### ✔ Pull Request

```
git checkout -b feature/sample-change
// make changes
git push
Go to GitHub → Create PR
```

### ✔ Merge

Merge the PR normally on GitHub.

All these events will appear immediately in the webhook dashboard.

---

## 🔔 GitHub Webhook Configuration

Configure a webhook in:

```
GitHub Repo → Settings → Webhooks
```

Use:

```
Payload URL: http://<ngrok-url>/webhook/receiver
Content-Type: application/json
Events: Send me everything
```

## 🧑‍💻 Author

**Goparaju Poorna Chand**

This repository is part of the **Techstax Webhook Developer Assignment**.

--- 
