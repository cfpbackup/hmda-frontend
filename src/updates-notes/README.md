# FAQ - News and Updates

## What is it?

The [News and Updates app](https://ffiec.cfpb.gov/updates-notes) provides a searchable change log of updates, releases, and corrections to published HMDA Data.

## Do content changes require redeployment?

No, just a pull request. Changes to [change-log.md](https://github.com/cfpb/hmda-frontend/blob/master/src/updates-notes/change-log.md) on the `master` branch are automatically deployed to production.

## How do I add a new entry to the News and Updates page?

You can edit the markdown file and open a pull request entirely on github.com. Here's how:

1. Log into github.com and go to the [change-log.md file](https://github.com/cfpb/hmda-frontend/blob/master/src/updates-notes/change-log.md). Click the top right pencil icon to "Edit this file".

2. Add your new entry at the top of the file. To do this, copy and paste the following markdown into the top of the file and edit it appropriately:

```markdown
---
date: MM/DD/YY
type: xxxxxxxxx
product: xxxxx
---
The content of the announcement goes here. You can **bold** things, _italicize_ things and add [links](https://example.com).

You can have multiple paragraphs of content and even include lists:

- List item one
- List item two
- List item three

```

3. Make sure the `date`, `type`, and `product` fields have [valid values](#fields).

4. After adding your new announcement, click the **"Commit changes..."** button, then select **"Create a new branch for this commit and start a pull request"**. Enter whatever you'd like for the pull request title and description.

5. After opening the pull request, GitHub will take a few minutes to build a preview of your changes and will post a comment on your PR once it's ready. Click the link in that comment to preview your changes on a temporary website.

6. Assign a front-end developer as a **Reviewer** on your pull request. You both can review the changes and merge when ready.

7. Merging the pull request will automatically deploy your changes to production.

### Fields

- `date`

  - Date the change will go live. Displayed entries are sorted by this date. Uses the format MM/DD/YY, e.g. 05/28/2026 for May 28, 2026.

- `type`

  - `announcement` - Platform or project-wide announcement
  - `release` - Newly released product or feature
  - `update` - Update to existing product not related to an error
  - `correction` - Modification to existing data to correct an error

    ![Types](./types.png)

- `product`

  - `mlar` - Modified LAR
  - `datasets` - Snapshot/Dynamic Datasets
  - `reports` - Disclosure/Aggregate Reports
  - `documentation` - Documentation pages
  - `tools` - Rate Spread/Check Digit/LARFT/FFVT
  - `filing` - Filing platform

## Format

Each entry is a markdown section with a YAML front matter block followed by a description, for example:

```markdown
---
date: 03/10/21
type: announcement | release | update | correction
product: mlar | datasets | reports | documentation | tools | filing
---
Description of the news update goes here.

```