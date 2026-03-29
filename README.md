# NIA — fitfornia.com

One-page brand site for NIA Activewear. Built as a single HTML file — no dependencies, no build step.

---

## Deploy to GitHub Pages

1. Create a GitHub account at github.com if you don't have one.
2. Create a new repository named `fitfornia-site` (public).
3. Upload `index.html` and `CNAME` to the repository (drag and drop on GitHub, or use the upload button).
4. Go to **Settings → Pages**.
5. Under **Source**, select `Deploy from a branch`, choose `main`, and save.
6. GitHub will publish the site at `https://<your-username>.github.io/fitfornia-site/` within a minute or two.

---

## Connect Your Custom Domain (fitfornia.com)

In your domain registrar (GoDaddy, Namecheap, Squarespace Domains, etc.), add these DNS records:

**A records** (point the root domain to GitHub Pages):
| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**CNAME record** (point `www` to your GitHub Pages URL):
| Type | Name | Value |
|------|------|-------|
| CNAME | www | `<your-github-username>.github.io` |

DNS changes can take a few hours to propagate.

Once DNS resolves, go to **Settings → Pages** in your GitHub repo and:
- Set the custom domain to `fitfornia.com`
- Check **Enforce HTTPS** (available once the certificate provisions, usually within 24 hours)

---

## Connect Mailchimp Email Signup

1. Create a free account at mailchimp.com.
2. Create an **Audience** (the list that will collect emails).
3. Go to **Audience → Signup forms → Embedded forms**.
4. Copy the `action` URL from the generated form code. It looks like:
   `https://youraccountname.us1.list-manage.com/subscribe/post?u=XXXXX&id=XXXXX`
5. Open `index.html` and find this comment:
   ```
   <!-- REPLACE THIS URL with your Mailchimp form action URL -->
   ```
6. Replace `YOUR_MAILCHIMP_FORM_ACTION_URL` in the `<form action="...">` attribute with your copied URL.
7. Also replace `b_PLACEHOLDER_ANTISPAM` in the hidden anti-bot field with the matching value from your Mailchimp form code.
8. Save and re-upload `index.html` to GitHub.

---

## Update Content

All content is in `index.html`. Open it in any text editor and search for what you want to change.

- **Social links:** search for `@LiftwithNia` — two instances in the footer
- **Copy/text:** every section is clearly commented
- **Colors:** all colors are CSS variables at the top of the `<style>` block

---

## Handoff to Shopify

When you're ready to launch the full store:
1. Set up your Shopify store.
2. In your domain registrar, update the DNS to point to Shopify instead of GitHub.
3. Archive or delete this repository.

The `index.html` and `CNAME` files can be kept as a backup of your pre-launch page.
