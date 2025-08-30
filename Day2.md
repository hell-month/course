---
marp: true
---

# Day 2

---

# Environments

- Production (prod)
- Staging (staging)
- Development (dev)
- Local (local)

---

# Dev environment vs local environment

- dev: testnet
- local: on your computer

---

# Why go local?

- Easier & faster testing & teardown
  - Gas
  - Smart contract deployment
- Full control of the environment

---

# Docker

- Docker: A tool that runs apps inside lightweight, isolated environments called containers.
- Image: A blueprint (frozen snapshot) used to create containers.
- Dockerfile: A text file with step-by-step instructions to build an image.
- Container: A running instance of an app packaged with everything it needs.
- Docker Compose: A tool to define and run multiple containers together using one simple config file.

---

# Local environment

- **nginx**: web server & reverse-proxy
- **ngrok**: tunnel
- **Smart contracts deployment**
- **EVM node (geth)**: blockchain
- **Explorer (blockscout)**: UI to see transactions and other data
- **Graph node stack**: index blockchain data & query
- DApp frontend
- DApp backend

---
<style scoped>
section {
  font-size: 27px;
}
</style>

# Assignment 1B submission
- Go to https://docs.google.com/spreadsheets/d/1LtR6zEHqmUgXdRn0NSkm2pmDreL8w3GBOMDGs7vVUGE/edit?usp=sharing and switch the sheet to **Assignment 1B**. Submit your info there.
- Make sure your forked https://github.com/hell-month/cohort-1-assignments to your account and updated the code for assignment 1B. Project setup may be checked. (If you already made changes to your fork, you will have to `git merge` or `git rebase` with [the upstream repository](https://github.com/hell-month/cohort-1-assignments))
- Deadline: 22:00 KST, Sept 8, 2025
- Leave the docker compose on from 10:00 PM of Sept 8 (Mon) to 01:00 AM Sept 9 (Tues)
- If the test fails, another chance will be given at the same time slot from Sept 9 Tues to Sept 10 Wed.
