# Bumart

**The campus marketplace for Bundelkhand University students.**
Live at **[bumart.vercel.app](https://bumart.vercel.app)**

Students graduate, shift hostels, and change semesters with piles of useful stuff — textbooks, cycles, calculators, lab coats — while the next batch buys the same things new. Bumart connects the two: list what you don't need, buy what you do, from people on your own campus.

> This repository is the public showcase. The production source code is private; this page documents what the product is, how it is built, and what it does.

## What it does

- **Listings** — post an item with photos, price, and category in under a minute; browse and search what your campus is selling.
- **Real-time chat** — buyers and sellers talk inside the app (Socket.io), no phone numbers exchanged with strangers.
- **Accounts that stay yours** — sign up and log in with JWT auth in http-only cookies; listings and chats are tied to your account.
- **Photo uploads** — images go straight to Cloudinary, so listing pages stay fast.
- **Built for discovery** — full SEO pass (sitemap, meta, structured data, Google Search Console) plus an `llms.txt` layer so AI search tools can read the site too.

## Stack

| Layer | Tech |
|---|---|
| Frontend | React, Vite, Tailwind CSS |
| Backend | Node.js, Express |
| Database | MongoDB Atlas |
| Realtime | Socket.io |
| Media | Cloudinary |
| Hosting | Vercel (frontend), Render (API) |

## How it is put together

The frontend is a React SPA that talks to a REST API. Auth is a JWT in an http-only cookie, so sessions survive refresh without exposing tokens to scripts. Chat runs over Socket.io on the same API server, with conversations stored in MongoDB so nothing is lost when you close the tab. Images never touch the API server — the browser uploads to Cloudinary and stores the returned URL.

## My role

Founder, and so far the whole team: product idea, design, the full stack, deployment, and the SEO. Bumart started as a problem I watched every semester in my own hostel corridor, and it is the project that taught me shipping beats perfect.

## Status

Live and in use at Bundelkhand University, Jhansi. Feedback and bug reports are welcome in the issues here.

**Harshit Bharti** · [Portfolio](https://harshit-portfolio-six-delta.vercel.app) · [LinkedIn](https://www.linkedin.com/in/harrshitbharrti)
