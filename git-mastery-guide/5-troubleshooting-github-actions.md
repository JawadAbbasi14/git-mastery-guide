🔍 Troubleshooting GitHub Actions
GitHub Actions powerful hain, lekin kabhi-kabhi issues aa sakte hain. Is section mein hum common problems aur unko debug karne ke tareeqe discuss karenge, taaki tum apne workflows ko smoothly chala sako.

💡 Common Problems & Solutions (Aam Masle Aur Hal)
1. Workflow Trigger Nahi Ho Raha (Workflow Not Triggering)
Problem: Tumne code push kiya ya PR banaya, lekin workflow run nahi hua.

Solution:

on Event Check Karo: Apni .github/workflows/*.yml file mein on: section ko dobara check karo. Kya event sahi define kiya gaya hai (e.g., on: push, on: pull_request)?

Branch Filtering: Agar on: push: branches: [main] jaisa kuch likha hai, to confirm karo ki tum usi branch par push kar rahe ho jo specify ki gayi hai.

Workflow File Path: Ensure karo ki tumhari YAML file .github/workflows/ directory ke andar hai.

Syntax Errors: YAML syntax errors ho sakte hain. GitHub Actions UI mein workflow run history mein jaakar dekho, wahan syntax errors dikh sakte hain.

2. Job/Step Fail Ho Raha Hai (Job/Step Failing)
Problem: Workflow run ho raha hai, lekin koi step ya poora job fail ho jata hai.

Solution:

Logs Check Karo: GitHub Actions UI mein fail hue workflow run par click karo, phir fail hue job aur step par click karo. Wahan detailed logs milenge jo batayenge ki kahan error aaya (e.g., command not found, permission denied, test failure).

Environment Variables: Agar env variables use kar rahe ho, to confirm karo ki unki values sahi hain aur wo correctly set kiye gaye hain.

Dependencies: Kya saari required dependencies (e.g., npm install, pip install) sahi se install hui hain?

Paths: Commands mein files ya directories ke paths sahi hain ya nahi, check karo.

continue-on-error: Agar kisi step ka fail hona poore workflow ko rokna nahi chahiye, to continue-on-error: true add kar sakte ho (lekin production ke liye careful raho).

3. Secrets Access Issue (Secrets Not Working)
Problem: Tum secrets use kar rahe ho, lekin workflow unko access nahi kar pa raha ya empty value mil rahi hai.

Solution:

Secret Name: Confirm karo ki secrets.MY_SECRET_KEY mein MY_SECRET_KEY wahi naam hai jo tumne GitHub repository settings mein Secrets section mein define kiya hai. Case-sensitive hota hai!

Scope: Secrets repository-level ya environment-level par set ho sakte hain. Ensure karo ki secret us scope mein available hai jahan tumhara workflow run ho raha hai.

Permissions: Deployment secrets ke liye, ensure karo ki tumhare workflow ke paas necessary permissions hain.

4. Permission Denied Errors
Problem: Workflow ko kisi file ya resource ko access karne ki permission nahi mil rahi.

Solution:

File Permissions: Agar tum koi script run kar rahe ho (.sh file), to ensure karo ki uske paas execute permissions hain (chmod +x your-script.sh).

GitHub Token Permissions: Agar workflow GitHub API se interact kar raha hai (jaise PR par comment karna), to permissions block mein required permissions add karo (e.g., pull-requests: write, contents: write). By default, GITHUB_TOKEN ke paas limited permissions hoti hain.

5. Caching Issues
Problem: Dependencies baar-baar install ho rahi hain ya cache sahi se kaam nahi kar raha.

Solution:

Cache Key: Ensure karo ki actions/cache action mein tumhari key sahi se define ki gayi hai, jo dependencies ke change hone par invalidate ho jaye (e.g., key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}).

Restore Keys: restore-keys ka use karo purane caches ko fallback ke taur par use karne ke liye.

🐞 Debugging Tips (Debug Karne Ke Tareeqe)
echo Statements: Apne steps mein echo statements add karo variables ki values print karne ke liye.

::debug:: Logs: Agar tum action mein custom messages print karna chahte ho jo debug logs mein dikhein, to ::debug::Your debug message syntax use karo.

Small Commits: Jab debugging kar rahe ho, to chote-chote commits karo aur har commit ke baad workflow run karo taaki problem ko isolate kar sako.

Local Testing: Agar possible ho, to apne build ya test commands ko local system par run karke dekho, taaki GitHub Actions se pehle basic issues solve ho sakein.

Ye troubleshooting guide tumhein GitHub Actions ke saath kaam karte waqt aane wali mushkilon ko hal karne mein madad karegi. Practice se tum in sab mein expert ho jaoge!

Iske saath hi, humari Git aur GitHub Actions ki series complete hoti hai! Kya tum kuch aur seekhna chahte ho ya in files mein koi aur enhancement chahiye?
