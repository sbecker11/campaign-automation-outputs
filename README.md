# Campaign Automation Outputs

This repository contains all generated campaign outputs (images, JSON files, etc.) from the campaign-automation tool.

## Structure

```
outputs/
└── campaigns/
    └── <campaign_id>_<timestamp>/
        ├── campaign_generated.json
        └── products/
            └── <product_id>/
                ├── <product_id>_generated.png
                └── <product_id>_resized_<aspect_ratio>.png
```

## Purpose

This repository is separate from the main `campaign-automation` code repository to:
- Keep the main repo focused on code
- Manage large binary files (images) separately
- Allow independent versioning and archiving of campaign outputs
- Reduce main repository size

## Usage

The main `campaign-automation` repository uses a symlink to access this directory, so scripts continue to work as before.

### Committing Campaign Outputs

After generating a campaign, commit the outputs to this repository:

```bash
cd campaign-automation-outputs
git add outputs/campaigns/<campaign_id>_<timestamp>/
git commit -m "Add campaign: <campaign_id>_<timestamp>"
git push
```

Or from the main repo directory:
```bash
cd ../campaign-automation-outputs
git add .
git commit -m "Add campaign outputs"
git push
```

