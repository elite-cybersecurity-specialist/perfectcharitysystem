# File purpose map

This map describes the full repository package. The implementation remains approximately 20% complete; the presence of a file or template does not establish that its intended workflow is complete.

## Root and folders

| Item | Purpose |
| --- | --- |
| [README.md](../README.md) | Staged public explanation and fourteen core visuals. |
| [codes/](../codes/) | Preserved Python application baseline. |
| [templates/](../templates/) | Twenty-nine prototype Jinja2 interface templates. |
| [assets/](../assets/) | Fourteen core PNG visuals, the official ECS digital name card and editable diagrams. |
| [config/](../config/) | Existing application, proxy and crawler configuration. |
| [docker/](../docker/) | Existing container and Compose definitions, awaiting entry-point integration. |
| [data/](../data/) | Empty-directory placeholder and tracked serialized model artifacts; runtime JSON is created by the app. |
| [uploads/](../uploads/) | Empty-directory placeholder for participant media and receipts. |
| [scripts/](../scripts/) | Existing shell and batch launchers, awaiting entry-point integration. |
| [requirements.txt](../requirements.txt) | Existing dependency pins. |
| [.env.example](../.env.example) | Example environment configuration; no private environment file is supplied. |
| [.gitignore](../.gitignore) | Source-control exclusions for local/runtime state. |
| [PCS.code-workspace](../PCS.code-workspace) | Editor workspace configuration. |
| [UPDATE-GITHUB.md](../UPDATE-GITHUB.md) | Extract, move selected changes into the existing checkout, review and push. |
| [UPDATE-FILES.txt](../UPDATE-FILES.txt) | Exact files to apply from this presentation update. |
| [GITHUB-ABOUT.txt](../GITHUB-ABOUT.txt) | Suggested repository About description, topics and website. |
| [PACKAGE-CONTENTS.json](../PACKAGE-CONTENTS.json) | Source provenance, package inventory and checksums. |

Git metadata is not included in the ZIP; an existing checkout retains its own history.

## Python source

| File | Purpose |
| --- | --- |
| [pcs-website.py](../codes/pcs-website.py) | Website routes, participant records, purchases, confirmations, allocations, projects and inspectors. |
| [perfectcharitysystem.py](../codes/perfectcharitysystem.py) | API application and core-module loading. |
| [pcs-crypto.py](../codes/pcs-crypto.py) | Prototype hash-linked blocks, transactions and balance calculation. |
| [pcs-wallet.py](../codes/pcs-wallet.py) | Wallet helpers and summaries. |
| [pcs-profiles.py](../codes/pcs-profiles.py) | Profile objects and management helpers. |
| [pcs_persistence.py](../codes/pcs_persistence.py) | JSON persistence and storage helpers. |
| [pcs_ai.py](../codes/pcs_ai.py) | Security assessment and monitoring code with optional ML dependencies. |

## Templates

| File | Purpose |
| --- | --- |
| [blockchain.html](../templates/blockchain.html) | Prototype block and transaction explorer. |
| [directory.html](../templates/directory.html) | Receiver and organisation directory. |
| [donate_pcs.html](../templates/donate_pcs.html) | Voluntary support for the PCS system profile. |
| [donate_project.html](../templates/donate_project.html) | Internal PCS contribution to a project. |
| [external_services.html](../templates/external_services.html) | Project/service description and supporting-file form. |
| [index.html](../templates/index.html) | Prototype landing page. |
| [inspector_add_coins.html](../templates/inspector_add_coins.html) | Manual PCS addition form. |
| [inspector_create_receiver.html](../templates/inspector_create_receiver.html) | Representative-created receiver or organisation form. |
| [inspector_edit_user.html](../templates/inspector_edit_user.html) | Inspector account-detail editing form. |
| [inspector_locations.html](../templates/inspector_locations.html) | Inspector location overview. |
| [inspector_user_detail.html](../templates/inspector_user_detail.html) | Inspector view of a participant account. |
| [inspector_users.html](../templates/inspector_users.html) | Inspector participant listing. |
| [login.html](../templates/login.html) | Login form. |
| [my_purchases.html](../templates/my_purchases.html) | Donor purchase requests and payment evidence. |
| [notifications.html](../templates/notifications.html) | Participant notifications. |
| [profile.html](../templates/profile.html) | Editable participant profile and activities. |
| [profile_inspector.html](../templates/profile_inspector.html) | Restricted inspector profile view. |
| [profile_public.html](../templates/profile_public.html) | Read-only participant profile template. |
| [profile_public_seo.html](../templates/profile_public_seo.html) | Public receiver profile template for external access. |
| [projects_list.html](../templates/projects_list.html) | Project listing. |
| [purchase_crypto.html](../templates/purchase_crypto.html) | Receiver selection for PCS purchases. |
| [purchase_crypto_detail.html](../templates/purchase_crypto_detail.html) | Selected receiver payment information and purchase request. |
| [rankings.html](../templates/rankings.html) | Prototype contribution rankings. |
| [register.html](../templates/register.html) | Donor registration form. |
| [search.html](../templates/search.html) | Participant search. |
| [sell_crypto.html](../templates/sell_crypto.html) | Receiver-side purchase requests and confirmation. |
| [upload_media.html](../templates/upload_media.html) | Profile video/media upload form. |
| [upload_picture.html](../templates/upload_picture.html) | Profile picture upload form. |
| [view_project.html](../templates/view_project.html) | Individual project details and records. |

## Documentation

| File | Purpose |
| --- | --- |
| [information.md](information.md) | High-level concept and reading guide. |
| [pcs-model.md](pcs-model.md) | Direct payments, PCS circulation, monthly allocation, valuation and accounting. |
| [pcs-governance.md](pcs-governance.md) | Participant profiles, directors, earnings, inspectors and SOPs. |
| [pcs-simple-controls.md](pcs-simple-controls.md) | Five minimal proposed enforcement controls. |
| [development-status.md](development-status.md) | Prototype components and remaining integration work. |
| [implementation.md](implementation.md) | Source architecture and implementation boundaries. |
| [deployment.md](deployment.md) | Local setup and current startup integration boundary. |
| [production.md](production.md) | Future production preparation and validation scope. |
| [image-plan.md](image-plan.md) | Final image order, intended message and caption notes. |
| [image-generation-prompts.json](image-generation-prompts.json) | Prompts for the seven generated illustrations. |
| [package-validation.md](package-validation.md) | Checks performed on this repository package. |
| [filepurpose.md](filepurpose.md) | This source and folder map. |

## Image assets

The cover uses the existing [Perfect-Charity-System.png](../assets/Perfect-Charity-System.png) path. Assets 02–14 retain their stable filenames from the latest image collection. The official digital card is [ECS-Official-Digital-Name-Card.jpeg](../assets/ECS-Official-Digital-Name-Card.jpeg).

Seven editable SVG explanatory panels are in [assets/diagrams/](../assets/diagrams/). Their PNG exports are the versions shown in the README. See [Image plan](image-plan.md).

## Existing infrastructure and model artifacts

- [config/config.py](../config/config.py), [config/apache.conf](../config/apache.conf) and [config/robots.txt](../config/robots.txt) retain their baseline contents.
- [docker/Dockerfile](../docker/Dockerfile), [Dockerfile.prod](../docker/Dockerfile.prod), [docker-compose.yml](../docker/docker-compose.yml) and [docker-compose.prod.yml](../docker/docker-compose.prod.yml) retain their baseline contents.
- [scripts/start.sh](../scripts/start.sh) and [start.bat](../scripts/start.bat) retain their baseline contents; see the startup notes before using them.
- [data/ml_models/](../data/ml_models/) contains anomaly_detector.pkl, feature_scaler.pkl, ip_reputation.pkl and threat_classifier.pkl. These tracked artifacts are copied and hash-checked, not retrained or executed during packaging.

Existing runtime account records, transaction JSON, receipts, uploads, secrets and Git metadata are not included as live data in this package.
