# carbanter.com: Banter's website

The public website for Banter: home page, privacy policy, terms of use, community rules,
support, and a page for forum owners and clubs. It is a plain static site with no build
step, hosted free on GitHub Pages at carbanter.com.

## What is in this folder

| File             | What it is                                                            |
| ---------------- | --------------------------------------------------------------------- |
| `index.html`     | Home page: what Banter does, the three levels, launch dates           |
| `privacy.html`   | Privacy policy (effective October 12, 2026)                           |
| `terms.html`     | Terms of use, including subscriptions                                 |
| `community.html` | Rules for Banter's own community and messages; reporting and blocking |
| `support.html`   | Help and common questions                                             |
| `owners.html`    | For forum owners and clubs                                            |
| `status.html`    | Community connections: in the feed, page only, not available (generated) |
| `data/site-list.json` | The export of the server's site list (host, status, risk) the status page is built from |
| `404.html`       | The page shown for an address that does not exist                     |
| `styles.css`     | The one stylesheet every page uses (light and dark)                   |
| `CNAME`          | Tells GitHub Pages the site's address: carbanter.com                  |

## The operator's name and address

Filled in on October 14, 2026: **Banter for Car Enthusiasts LLC** (New York, DOS ID
8044129, formed October 13, 2026), and the town only, **Stony Brook, New York**, so the
owner's home street address is not published. If a street or mailbox address is wanted
later (a virtual mailbox, for example), Claude replaces "Stony Brook, New York" in the
privacy policy, terms and owners page.

## How to publish

About 20 minutes of your time, then up to a day of waiting for the internet to pick up the
new address. GitHub's own instructions are the source for every value below (see
"Sources" at the end).

### Step 1. Create the repository on GitHub

1. Sign in to github.com as **pbaginski86** (the account that holds the Banter app).
2. Click the **+** at the top right, then **New repository**.
3. Repository name: **carbanter-site**.
4. Choose **Public**. GitHub Pages is free only for public repositories on a free account.
5. Leave "Add a README file" unticked, so the repository starts empty. Click
   **Create repository**.
6. Then either:
   - **Let Claude do it:** tell Claude "the carbanter-site repository exists". Claude will
     put every file in it. Or
   - **Do it yourself:** on the new repository's page, click **uploading an existing file**,
     drag in every file from this folder (including `CNAME`), and click **Commit
     changes**.

### Step 2. Verify the domain (recommended by GitHub)

This stops anyone else on GitHub from using carbanter.com.

1. On GitHub, click your picture at the top right, then **Settings** (your profile
   settings, not the repository's).
2. In the left column, under "Code, planning, and automation", click **Pages**.
3. Click **Add a domain**, type **carbanter.com**, and click **Add domain**.
4. GitHub shows one **TXT record** (a name starting with `_github-pages-challenge-` and a
   value). Keep that page open and add the record at Squarespace (Step 5 explains where:
   choose type **TXT**, and copy the name and value exactly as GitHub shows them).
5. Come back and click **Verify**. If it is not ready yet, try again later from the same
   page. Leave the TXT record in place for good.

### Step 3. Turn on GitHub Pages

1. Open the **carbanter-site** repository and click **Settings** (the gear tab).
2. In the left column, click **Pages**.
3. Under "Build and deployment", under "Source", choose **Deploy from a branch**.
4. Under "Branch", choose **main** and the folder **/ (root)**, then click **Save**.

### Step 4. Set the custom domain

1. On the same Pages settings page, under "Custom domain", type **carbanter.com** and click
   **Save**.
2. GitHub then checks the address. It will show a warning until Step 5 is done and has
   taken effect; that is expected.

### Step 5. Add the address records at Squarespace Domains

1. Sign in at **account.squarespace.com/domains** and open **carbanter.com**.
2. Open **DNS**, then **DNS settings**.
3. If you see a group of records called **Squarespace Defaults**, delete that group. Those
   records point carbanter.com at Squarespace and would clash with GitHub. Do **not**
   delete records for email (type **MX**, or a preset for Google Workspace or another email
   service): they are what makes hello@, support@ and the other addresses work.
4. Under **Custom records**, add these records one at a time. "Host" is what Squarespace
   calls the record name; `@` means carbanter.com itself. Leave the time setting (TTL) as
   Squarespace suggests.

| Host  | Type  | Points to (value)       |
| ----- | ----- | ----------------------- |
| `@`   | A     | `185.199.108.153`       |
| `@`   | A     | `185.199.109.153`       |
| `@`   | A     | `185.199.110.153`       |
| `@`   | A     | `185.199.111.153`       |
| `www` | CNAME | `pbaginski86.github.io` |

Optional, for newer internet connections (IPv6). GitHub recommends keeping the four A
records as well if you add these:

| Host | Type | Points to (value)     |
| ---- | ---- | --------------------- |
| `@`  | AAAA | `2606:50c0:8000::153` |
| `@`  | AAAA | `2606:50c0:8001::153` |
| `@`  | AAAA | `2606:50c0:8002::153` |
| `@`  | AAAA | `2606:50c0:8003::153` |

Three things GitHub warns about:

- The `www` record must point to **pbaginski86.github.io** exactly, without the repository
  name, and not to carbanter.com.
- Do not add a "wildcard" record (a host of `*`). GitHub says it exposes the domain to
  takeover.
- With both carbanter.com and www set up, GitHub sends visitors of www.carbanter.com to
  carbanter.com automatically.

### Step 6. Turn on the secure connection

1. Wait. The new records can take effect at once or take up to 24 hours.
2. Return to the repository's **Settings**, then **Pages**. When GitHub shows that the DNS
   check succeeded, tick **Enforce HTTPS**. GitHub says this option can take up to 24
   hours to become available.

### Step 7. Check it

Open **carbanter.com** and **www.carbanter.com** on your phone and on a computer. Both
should show the Banter home page with a padlock in the address bar. Tap each link in the
footer. Then tell Claude it is live, so the address can be used in the app stores'
privacy policy and support fields.

## Where the live copy is

The public repository `pbaginski86/carbanter-site` holds a copy of this folder (first push
October 14, 2026, commit `02df6a2`). This folder in the Banter repository is the source;
a change is made here first, then copied to a clone of `carbanter-site` and pushed, and
GitHub Pages updates the live site within minutes.

## Updating the site later

Ask Claude for the change. Claude edits the files and, once it can reach the repository,
publishes them; GitHub updates the live site within a few minutes. Keep the `CNAME` file:
if it is removed, the custom domain is lost.

## Worth knowing

- **Email addresses:** the site lists hello@, support@, privacy@, partners@ and
  press@carbanter.com. Each must actually receive mail before launch (Apple and Google
  reviewers write to the support and privacy addresses).
- **If the site is ever switched off** on GitHub while the Squarespace records still
  point to it, GitHub advises removing the records at once, unless the domain is verified
  (Step 2).
- **GitHub's limits:** GitHub Pages is not for sites that mainly sell things or run a
  service. This site only describes the app and links to the stores, which fits; payments
  happen in the App Store and Google Play.

## Sources

GitHub Docs, read from GitHub's documentation source on October 12, 2026:

- Managing a custom domain for your GitHub Pages site:
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
  (the A and AAAA addresses, the www CNAME rule, the wildcard warning, Enforce HTTPS)
- Verifying your custom domain for GitHub Pages:
  https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- Configuring a publishing source for your GitHub Pages site:
  https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub Pages limits:
  https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits

Squarespace's own help on adding DNS records (not read for this guide; the menu names in
Step 5 may differ slightly):

- DNS records for web hosting:
  https://support.squarespace.com/hc/en-us/articles/31119879125645-DNS-records-for-web-hosting

## The status page

`status.html` is written by `npx tsx scripts/build-site-status.ts` (run from the
repository root) from `registry/` and `data/site-list.json`, with the same rules the app
uses (`resolveAccess`). After the server's site list changes, refresh the export through the
Supabase connector (`select host, status, risk from public.site_policy order by host`, written
to `data/site-list.json` with the date), run the script, and publish. The page never prints
the server's notes on a site; its reasons are the few neutral sentences in the script.
