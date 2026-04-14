# MDC Home Services - Website

A premium static website for MDC Home Services. Built in plain HTML/Tailwind with zero build step. Deploys free to Cloudflare Pages.

## What's in this folder

- `index.html` - Home
- `home-care-plan.html` - $99/month Home Care Plan landing page
- `remodeling.html`, `bathrooms.html`, `basements.html`, `decks.html`, `handyman.html` - Service pages
- `about.html` - About
- `contact.html` - Contact with form
- `assets/styles.css` - Custom styles beyond Tailwind

## Before you launch: 3 things you must do

### 1. Replace the phone number placeholder
Search every `.html` file for `[PHONE]` and replace with your actual business number. It appears in the header CTAs, hero CTAs, and footer. Fastest way on Mac: open the folder in any text editor (VS Code, Sublime, BBEdit) and use Find in Folder.

You also need to replace it in the `tel:[PHONE]` links so the tap-to-call works. Use format `tel:6105551234` (no spaces or dashes).

### 2. Replace license placeholders
Search for `[LICENSE]` in every file and replace with your PA HIC and NJ HIC numbers.

### 3. Set up the contact form
The contact form is currently pointing at a placeholder Formspree endpoint. Here's how to wire it up, 5 minutes:

1. Go to https://formspree.io and create a free account with mark@mdchomeservices.com
2. Create a new form. Name it "MDC Contact"
3. Copy the form ID (looks like `xyzabcde`)
4. Open `contact.html`, find this line:
   ```
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST"
   ```
5. Replace `YOUR_FORM_ID` with your actual ID.
6. Formspree free tier gives you 50 submissions per month. If you outgrow it, $10/month for unlimited.

Alternative: if you'd rather use Cloudflare's built-in form handling (Pages Functions), tell me and I'll wire it up. Free, no third party.

## Optional before launch

### Replace the 3 placeholder testimonials on the home page
Open `index.html`, search for `Placeholder testimonials`. Replace the three blockquotes with real client quotes. Keep it short, specific, and signed with first name + location (e.g., "Sarah M., Bryn Mawr"). Real quotes beat any copy I could write.

### Real photos
Right now the hero sections are solid navy gradients. That's intentional, placeholder gradients look cleaner than stock photos. When you have real project photos, I can swap them in. Use them in:
- Home hero background
- Service page hero backgrounds
- A new "Selected Work" section on the home page (highly recommended)

Shoot for 5-10 photos: one hero shot per service, plus a gallery. iPhone photos in good light are fine, don't overthink it.

## How to deploy (free) - Cloudflare Pages

Easiest path. No command line needed.

### Option A: Drag and drop (5 minutes)

1. Go to https://pages.cloudflare.com
2. Sign up with mark@mdchomeservices.com (free account, no credit card)
3. Click "Create a project"
4. Click "Direct Upload" (not Git)
5. Name the project `mdc-home-services`
6. Drag this entire folder onto the upload area
7. Click Deploy
8. Cloudflare gives you a URL like `mdc-home-services.pages.dev`. Site is live.

### Option B: Git (if you want version control)

1. Create a free GitHub account if you don't have one
2. Create a new private repo called `mdc-website`
3. Upload this folder to the repo
4. In Cloudflare Pages, connect your GitHub and select the repo
5. Build settings: leave blank (no build step, this is static HTML)
6. Deploy

### Point mdchomeservices.com at the new site

Once the Pages site is live at `mdc-home-services.pages.dev`:

1. In Cloudflare Pages, go to your project → Custom domains
2. Click "Set up a custom domain"
3. Enter `mdchomeservices.com`
4. Cloudflare will walk you through DNS. If your domain is already on Cloudflare, it's one click. If not, you'll need to point your registrar's nameservers to Cloudflare.
5. Also add `www.mdchomeservices.com` as a redirect to the root domain.

Cloudflare issues free SSL automatically. Site is live under your real domain within 15 minutes.

## Keeping Jobber in place

Jobber remains your operations software: scheduling, CRM, invoicing, work orders. Nothing changes there. The only thing you're moving off Jobber is the public website.

The contact form on this site feeds into Formspree (or wherever you wire it) and sends you an email. You take that email and create a lead in Jobber manually, or wire up a Zapier between Formspree and Jobber if you want it automated. $20/month for Zapier Starter tier if you get that far.

## Editing content later

Static HTML is easy to edit in any text editor. If you want a visual CMS so you or a team member can edit copy without touching code, we can add Decap CMS on top of this. Free, lives on the same files. Tell me when you want that.

## Cost summary

- Hosting: $0 (Cloudflare Pages free tier)
- Domain: already owned
- Form handling: $0 (Formspree free tier, 50/month) or $10/month unlimited
- SSL cert: $0 (automatic)
- Total: $0 to launch, maybe $10/month at scale

## Questions for me

When you're ready to launch or add real photos, testimonials, a gallery section, a blog, or anything else, come back and tell me what you need. This codebase is simple enough I can add any of that in minutes.
