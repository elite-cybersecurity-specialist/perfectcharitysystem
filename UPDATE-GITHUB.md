# Apply the PCS image and public presentation update

Prepared 28 November 2026. Download `PCS_GitHub_Image_Update_20261128.zip` into `~/Downloads/`.

The archive is an overlay for your existing checkout. Its exact replacement paths are listed in [UPDATE-FILES.txt](UPDATE-FILES.txt). The seven diagram PNGs and SVGs retain their established asset filenames. The cover, illustrated awareness artwork and official name card remain unchanged. The approved completion estimate is approximately **5%**.

## Extract into the existing checkout

```bash
cd ~/Downloads/GitHub/perfectcharitysystem
git status --short --branch
unzip -l ~/Downloads/PCS_GitHub_Image_Update_20261128.zip
unzip -o ~/Downloads/PCS_GitHub_Image_Update_20261128.zip -d .
```

Review existing local edits before applying replacements. This archive contains only presentation paths; your repository directory, code, templates, configuration, model files, account data, uploads and Git history remain in the existing checkout.

## Stage the listed files, review, commit and push

```bash
cd ~/Downloads/GitHub/perfectcharitysystem
while IFS= read -r pcs_update_path; do
    [ -n "$pcs_update_path" ] || continue
    git add -- "$pcs_update_path"
done < UPDATE-FILES.txt
git diff --cached --stat
git diff --cached -- README.md documentation UPDATE-GITHUB.md
git commit -m "Clarify PCS diagrams and public explanation"
git push
git status --short --branch
```

Review the staged changes before committing, including any files staged before this update. These commands use the existing repository, authentication and remote. No commit or push has been performed by the file-generation process.

## Update the existing Blogger post after the asset push

Paste the complete separately supplied `ECS_Blogger_Perfect_Charity_System_20261128.html` into the existing PCS post’s HTML editor. Keep the established permalink: [https://elite-cybersecurity-specialist.blogspot.com/2026/11/perfect-charity-system.html](https://elite-cybersecurity-specialist.blogspot.com/2026/11/perfect-charity-system.html). Preview mobile and desktop layouts, then save the post update.

The public explanation directs readers to the website. No document file, embed or download button is part of this update. Keep the current main-theme XML and its approved red Battle Offensive AI styling.

See [Package validation](documentation/package-validation.md) for the precise checks and publication boundary.
