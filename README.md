- 👋 Hi, I’m @kiridharan
- 👀 I’m interested in web dev & Machine learning , app development , XR
- 🌱 I’m currently learning django , flutter , javascript 

- 💞️ I’m looking to collaborate on project based on flutter, django 
- 📫 How to reach me @k.i.r.i.d.h.a.r.a.n

<!---
kiridharan/kiridharan is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
on:
  schedule:
    - cron: '0 */12 * * *' # every 12 hours
  push:
    branches:
      - master
      - main
jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
      with:
        fetch-depth: 0
    - name: Generate README.md
      uses: teoxoy/profile-readme-stats@v1
      with:
        token: ${{ secrets. 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  }}
    - name: Update README.md
      run: |
        if [[ "$(git status --porcelain)" != "" ]]; then
        git config user.name github-actions[bot]
        git config user.email 41898282+github-actions[bot]@users.noreply.github.com
        git add .
        git commit -m "Update README"
        git push
        fi
