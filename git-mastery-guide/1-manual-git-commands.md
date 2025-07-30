⚙️ GitHub Actions - Buniyadi Baatain
GitHub Actions tumhare Git workflows ko automate karta hai.
Iska matlab hai jab tum code push karo ya pull request banao, to testing, deployment, ya notifications jese kaam khud-ba-khud ho jayenge — bina tumhare kuch kiye.

🧱 GitHub Actions Ka Dhaancha
GitHub Actions ki files YAML format mein .github/workflows/ folder mein hoti hain. Har file ek alag workflow hai.

name: Meri Pehli GitHub Action # Workflow ka naam

on: push # Ye batata hai kab workflow chalega (trigger)

jobs: # Ye jobs ka collection hai
  build: # Job ka ID
    runs-on: ubuntu-latest # Kis OS par job chalega

    steps: # Job ke andar chalne wale commands ya actions
      - name: Code checkout karo # Step ka naam
        uses: actions/checkout@v4 # Repository ko checkout karne wala action

      - name: Ek script chalao # Simple command
        run: echo "Hello GitHub Actions!"

      - name: Dependencies install karo # Dependencies install karna
        run: npm install # Ya `pip install -r requirements.txt`

      - name: Tests chalao # Tests run karna
        run: npm test # Ya `pytest`

Aham Hissay (Key Components)
name: Workflow ka naam.

on: Workflow kab trigger hoga (e.g., push, pull_request, schedule).

jobs: Ek workflow mein ek ya zyada jobs ho sakte hain.

runs-on: Virtual environment (e.g., ubuntu-latest).

steps: Har job ke andar commands ya actions ki list.

name: Step ka naam.

uses: Pre-built GitHub Action use karna.

run: Command-line commands chalana.

🚀 Aam Istemaal (Common Use Cases)
GitHub Actions se bahut saare kaam automate ho sakte hain:

Continuous Integration (CI) - Testing:

Code push hone par automatic tests chalana.

Code quality check karna.

Continuous Deployment (CD) - Deployment:

Code merge hone ke baad automatic deployment karna.

Notifications:

Build fail hone par Slack ya email par notification bhejna.

✨ Behtareen Tareeqe (Best Practices)
Secrets Use Karo: Sensitive information (API keys) ko GitHub Secrets mein rakho, code mein hardcode mat karo.

Workflow Reusability: Common steps ko reusable workflows mein badlo.

Version Pinning: Actions ke specific version ko use karo (@v4).

Small & Focused Workflows: Workflows ko chota aur ek hi kaam par focus rakho.

Error Handling: Failures ko manage karne ke liye steps mein error handling add karo.
