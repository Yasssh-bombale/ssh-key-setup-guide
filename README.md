# How to Set Up SSH Key in Your Local System

Follow the steps below to generate and configure an SSH key for secure authentication with GitHub from your local development environment.

---

## 🔍 Step 1: Check for Existing SSH Keys

Before generating a new SSH key, check if any existing keys are present:

```bash
ls ~/.ssh
```

If you find existing SSH keys (e.g., `id_ed25519` and `id_ed25519.pub`), you may choose to remove them to avoid conflicts:

```bash
rm ~/.ssh/id_ed25519
rm ~/.ssh/id_ed25519.pub
```

---

## 🔐 Step 2: Generate a New SSH Key

Generate a new SSH key using your email address (associated with your GitHub account):

```bash
ssh-keygen -t ed25519 -C "youremail@gmail.com"
```

After successful generation:

1. Start the SSH agent:

   ```bash
   eval "$(ssh-agent -s)"
   ```

2. Add your new SSH key to the agent:
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

---

## 📋 Step 3: Copy the Public SSH Key

To view and copy your public SSH key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the entire output and proceed to the next step.

---

## 🔗 Step 4: Add the SSH Key to Your GitHub Account

1. Go to [GitHub SSH Settings](https://github.com/settings/ssh).
2. Click on **"New SSH key"**.
3. Paste the copied public key.
4. Save the key.

---

## 🛠️ Step 5: Update Remote URL in Your Code Editor

Update the remote URL of your Git repository to use the SSH format:

```bash
git remote set-url miit git@github.com:edubuk/MIIT-Screening-V2.git
```

Make sure you're using the correct remote name (`origin`, `miit`, etc.) based on your configuration.

---

## ✅ You’re All Set!

You’ve successfully set up your SSH key. You can now securely push and pull code to and from your GitHub repository without needing to enter your username and password each time.
