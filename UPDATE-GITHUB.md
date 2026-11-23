# Apply the full repository presentation update

This ZIP contains the complete tracked source snapshot plus the new README, aligned documentation, fourteen core visuals, the official ECS digital name card and seven editable SVG diagrams.

The application code, templates, configuration, requirements, launchers, Docker files and model artifacts are preserved from the GitHub baseline. To update your existing checkout, move only the new or changed presentation files listed in UPDATE-FILES.txt. There is no need to replace its source directories, Git metadata or runtime state.

## 1. Extract into a separate staging folder

Download Perfect-Charity-System-Full-Repository-20261123.zip into your Downloads folder. In Bash:

```bash
unzip -o "$HOME/Downloads/Perfect-Charity-System-Full-Repository-20261123.zip" -d "$HOME/Downloads/PCS-Full-Repository-Staging-20261123"

pcs_package="$HOME/Downloads/PCS-Full-Repository-Staging-20261123/perfectcharitysystem"
pcs_checkout="$HOME/Downloads/GitHub/perfectcharitysystem"

cd "$pcs_checkout"
git rev-parse --show-toplevel
git remote -v
git status --short --branch
```

Use the existing checkout on main with its existing origin remote. If the status shows local changes, review them before moving replacement files. This package intentionally replaces the README, the main cover and aligned documentation without making backup copies.

## 2. Review the exact update list

```bash
cat "$pcs_package/UPDATE-FILES.txt"
```

The list contains the new or changed presentation files and package documentation. It does not include application source, runtime JSON, uploads, private environment files or Git metadata.

## 3. Move the listed files into the existing checkout

Run this block once after extracting the package:

```bash
while IFS= read -r pcs_relative; do
    [ -n "$pcs_relative" ] || continue
    mkdir -p "$(dirname "$pcs_checkout/$pcs_relative")"
    mv -f -- "$pcs_package/$pcs_relative" "$pcs_checkout/$pcs_relative"
done < "$pcs_package/UPDATE-FILES.txt"
```

File numbers in assets are stable identifiers, not the reading order. The cover keeps the existing assets/Perfect-Charity-System.png path; the README places every image in its intended stage.

## 4. Stage, review, commit and push

```bash
cd "$pcs_checkout"

while IFS= read -r pcs_relative; do
    [ -n "$pcs_relative" ] || continue
    git add -- "$pcs_relative"
done < "$pcs_checkout/UPDATE-FILES.txt"

git diff --cached --stat
git diff --cached -- README.md documentation
git commit -m "Present PCS donation cycle, monthly limits and accountable charity model"
git push origin main
git status --short --branch
```

The repository is already initialised. Do not run git init, replace the checkout folder or force-push. If the push reports remote changes, reconcile them with a normal merge or rebase after reviewing the state.

## 5. Update the About panel

The new GITHUB-ABOUT.txt is in the checkout after the move. Use its description, topics and website in GitHub's About panel if desired.

## A complete source copy is also included

The rest of the extracted folder is the verified source baseline for reference or a separate fresh development copy. Keeping it in the ZIP makes this a full repository package rather than an image-only update. It does not contain Git history, real participant data or private environment configuration.

The approximately 20% development status remains explicit. Packaging and documentation completion are separate from application completion; see [Development status](documentation/development-status.md).
