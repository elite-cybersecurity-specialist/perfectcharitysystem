# Update the existing GitHub checkout

This full working-tree ZIP contains the updated README, fifteen core visuals, the ECS name card, eight editable diagrams, aligned documentation and the uploaded application baseline. Git history and private runtime data are excluded.

Download **PCS-GitHub-Update-20261128.zip** into your Downloads folder. The repository at `~/Downloads/GitHub/perfectcharitysystem` is already initialised and connected to its existing `origin`; use that checkout.

## Unzip, transfer, commit and push

The block extracts into a separate staging folder and copies only files listed in `UPDATE-FILES.txt`. Application source, templates, private environment configuration, runtime data and existing Git history are not on that update list. Local changes must be saved or committed before replacement.

```bash
(
  set -e
  pcs_stage="$(mktemp -d "$HOME/Downloads/pcs-update.XXXXXX")"
  unzip "$HOME/Downloads/PCS-GitHub-Update-20261128.zip" -d "$pcs_stage"
  pcs_package="$pcs_stage/perfectcharitysystem"

  cd "$HOME/Downloads/GitHub/perfectcharitysystem"
  if [ -n "$(git status --porcelain)" ]; then
    echo "Save or commit the existing local changes before applying this update."
    exit 1
  fi
  git switch main
  git pull --ff-only origin main

  while IFS= read -r pcs_file; do
    mkdir -p "$(dirname "$pcs_file")"
    cp -a -- "$pcs_package/$pcs_file" "$pcs_file"
  done < "$pcs_package/UPDATE-FILES.txt"

  git add --pathspec-from-file=UPDATE-FILES.txt
  git diff --cached --stat
  git commit -m "Update PCS README, profiles and governance artwork"
  git push origin main
  git status --short --branch
)
```

The staged diff summary is printed before the commit. A failure stops the block. A normal pull or push conflict must be resolved using the actual repository state; no force push is included.

## What is included

The main cover keeps `assets/Perfect-Charity-System.png`. Images 08 and 11 replace their earlier versions, and 15 adds the complete profile activity example. Its participant and location labels are generic. The README places the logical-flow artwork near the beginning and integrates all images in reading order.

The complete original application tree is included for reference. Only the changed presentation and documentation paths are applied by the command block, so it cannot roll newer application source back to the supplied snapshot.

The About description in [GITHUB-ABOUT.txt](GITHUB-ABOUT.txt) can be copied into GitHub's About panel separately. No public PDF download or Blogger edit is included. Software development remains self-funded and approximately 5% complete.
