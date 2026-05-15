name: GitHub-Profile-3D-Contrib

on:
  schedule:
    - cron: "0 18 * * *"   # Runs daily at 18:00 UTC
  workflow_dispatch:        # Allows manual trigger from Actions tab

jobs:
  build:
    runs-on: ubuntu-latest
    name: Generate 3D Contribution Graph

    steps:
      - uses: actions/checkout@v3

      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: AtharvaPatil31
          SETTING_JSON: |
            {
              "githubUserName": "AtharvaPatil31",
              "startForegroundColor": "#3B82F6",
              "endForegroundColor": "#00ff99",
              "backgroundColor": "#0d1117",
              "type": "rainbow"
            }

      - name: Commit & Push
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "github-actions[bot]@users.noreply.github.com"
          git add -A
          git diff --staged --quiet || git commit -m "chore: update 3D contribution calendar"
          git push
