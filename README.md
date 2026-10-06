# NUO Life

**Your life shouldn't live in your head.**
NUO brings your calendar, reminders, money and everyday commitments together, so you always know what matters next. A calm life-admin app for UK adults, designed with ADHD in mind. Type something the way you'd say it, and NUO puts it where it belongs on one timeline.

> Commercial product built under NUO Tech. **Production source code is private.** This repository is a showcase of the product, the design and the engineering behind it.

### [View the live product →](https://nuolife.app)

<p align="center"><img src="docs/screenshots/web/hero.png" alt="The NUO Life website, with a playable demo of the Today screen" width="860" /></p>

## What it is

- **An iPhone app** (Expo / React Native). Your timeline is stored on the device today, and NUO is designed so you choose what it connects to.
- **A website** (Next.js) that shows the product through small living demos, lets you play with a sample phone, and powers the one feature that has to leave the phone: shareable availability links.
- **A product, not a prototype**: Free and Premium plans, a waitlist, a continuous-deployment pipeline and one visual language across app and site.

### The product in one picture

NUO is **Life + Money** for everyone, with **Home** and **Business** as optional modes that appear when you need them. One timeline sits underneath all of it.

<p align="center">
  <img src="docs/screenshots/app/insights-time.png" alt="Insights in the app: week ahead and the monthly wrap" width="250" />
  &nbsp;
  <img src="docs/screenshots/app/wrap-money.png" alt="A Money chapter slide from Wrapped" width="250" />
  &nbsp;
  <img src="docs/screenshots/app/wrap-card.png" alt="The shareable card for the whole month" width="250" />
</p>
<p align="center"><sub>The iPhone app (simulator, sample data): Insights, a Money chapter of Wrapped, and the card made to share.</sub></p>

## Features

### Capture: type it once, it goes where it belongs
A hand-written, on-device parser turns a sentence into a structured item: title, date and time, repeat, amount and category (Life, Money, Home). It never invents a time you didn't give, and everything stays editable. The website shows it working: a sentence types in, NUO reads it, and it lands on a small timeline.

<p align="center"><img src="docs/screenshots/web/capture.png" alt="Capture demo on the website" width="780" /></p>

### Money, in context
Bills, income, subscriptions and renewals sit on the same timeline as the rest of your life, and Money insights are worked out from the commitments you add to NUO: income, known commitments, what's left, and a projected year, with the working shown. It is deliberately not a budgeting app: no spending categories, no charts of where your coffee money went. The model treats where the figures come from as separate from what they mean, so other sources can feed it later without changing the product.

<p align="center"><img src="docs/screenshots/web/money.png" alt="Money section on the website" width="780" /></p>

### Home, Business and the Insights recap
Home keeps mortgage dates, insurance, repairs and renewals together. Business is an optional mode for income, expenses and deadlines. Insights turns a month into a recap that builds itself.

<p align="center"><img src="docs/screenshots/web/home.png" alt="Home section" width="380" />&nbsp;<img src="docs/screenshots/web/insights.png" alt="Insights recap section" width="380" /></p>

### One Wrapped per month
Wrapped is one story for your whole month, made of **chapters**: Life, Money, Home and Business, each in its own colour. It ends in a single card made to share.

- **Month first.** The Wraps screen lists months, not categories. A month is the thing you open.
- **Chapters appear only when there is something to say.** Home and Business show when those managers are on and have data. Free members get Life and Money; Premium adds Home and Business. Nothing shows empty.
- **Private by default.** The shared card carries counts only. Names and £ amounts appear only when you switch them on, and each figure says what it is and for which month.
- **A share sheet** with X, copy image, copy caption, save image and the system sheet.

<p align="center">
  <img src="docs/screenshots/app/wrap-money.png" alt="Money chapter" width="210" />
  &nbsp;
  <img src="docs/screenshots/app/wrap-home.png" alt="Home chapter" width="210" />
  &nbsp;
  <img src="docs/screenshots/app/wrap-card.png" alt="The month card" width="210" />
</p>
<p align="center"><img src="docs/screenshots/web/wrapped.png" alt="The Wrapped section on the website: the month in the middle, its four chapters either side" width="860" /></p>

### Scheduled email you approve
Write it now, send it when it matters, with you in control. The flow is explicit: needs your approval, scheduled, sent. Nothing goes out without approval, and it only shows as sent once the provider confirms.

<p align="center"><img src="docs/screenshots/web/email.png" alt="Scheduled email section" width="780" /></p>

### Designed with ADHD in mind
One thing at a time on Today, "still open" instead of "overdue", and a section that shows it rather than telling you: the same morning without and with NUO.

<p align="center"><img src="docs/screenshots/web/adhd.png" alt="ADHD section: without and with NUO, and still open, never overdue" width="780" /></p>

### Trust and pricing
Four plain principles (you choose what NUO knows, you control the actions, private by design, your data isn't the product) and a simple split: **Free brings your life together. Premium helps you handle it.**

<p align="center"><img src="docs/screenshots/web/trust.png" alt="Trust section" width="380" />&nbsp;<img src="docs/screenshots/web/pricing.png" alt="Pricing section" width="380" /></p>

## The website mirrors the app

The hero is a playable Today screen on in-memory sample data. Its Insights screens, Time and Money, are rebuilt from the app's real layout, with Money open as a Premium preview. Nothing typed is saved or sent, and it clears when you leave.

<p align="center">
  <img src="docs/screenshots/demo-phone/today.png" alt="Demo phone: Today" width="250" />
  &nbsp;
  <img src="docs/screenshots/demo-phone/insights-time.png" alt="Demo phone: Insights, Time" width="250" />
  &nbsp;
  <img src="docs/screenshots/demo-phone/insights-money.png" alt="Demo phone: Insights, Money" width="250" />
</p>

### Responsive by design, not by squashing
The five-card Wrapped composition is a desktop layout. Below 900px it becomes a one-card slideshow that moves by itself, with the next card peeking in, and respects reduced motion.

<p align="center">
  <img src="docs/screenshots/web-mobile/hero.png" alt="Mobile hero" width="220" />
  &nbsp;
  <img src="docs/screenshots/web-mobile/capture.png" alt="Mobile capture demo" width="220" />
  &nbsp;
  <img src="docs/screenshots/web-mobile/wrapped.png" alt="Mobile Wrapped slideshow" width="220" />
</p>

<p align="center"><img src="docs/screenshots/web/free-vs-premium.png" alt="The Free vs Premium page" width="620" /></p>

## Stack

| Layer | Technology |
| --- | --- |
| iPhone app | Expo SDK 57, React Native 0.86, React 19, TypeScript |
| Device integrations | EventKit (via `expo-calendar`), local notifications, secure storage, haptics, image rendering, clipboard, photo-library save and the system share sheet for Wrapped |
| Website and API | Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS 4, route handlers |
| Hosting and delivery | Vercel, GitHub Actions |
| Data | On-device store for personal data. Server side: shared availability records only (development storage is a JSON file; a database is planned before launch) |
| Quality gates | ESLint 9, `tsc --noEmit`, production build on every pull request |

## Engineering highlights

- **Natural-language capture.** A hand-written, on-device parser turns sentences into structured items: dates and ranges, repeats, amounts, categories and several entries from one sentence. It never invents a time you didn't give.
- **Calendar and reminder integrations.** Reads and writes Apple Calendar and Reminders through EventKit, including Gmail and Outlook calendars added to the iPhone, and keeps ticks in step in both directions.
- **Approval-first automations.** Items carry a mode (you, assisted, auto, watch) and a state machine (scheduled, needs approval, done, failed, cancelled) with an audit trail. Nothing goes out without approval, and it only shows as sent once it has been.
- **A unified monthly Wrapped model.** One pure builder, `buildWrappedMonth(source, month)`, composes a month from chapter builders (Life, Money, Home, Business). It returns `chapters[]`, the full slide list, per-chapter start positions and one share card. Chapters with nothing meaningful are omitted. History length is a single rule (`wrapMonthsFor`), not a deletion, and the same chapter model can be aggregated into a year later.
- **Privacy-aware sharing.** The share card has a counts-only default and an amounts variant behind a switch. Figures carry their context ("left after known commitments", "income in September"). The layout is measured at runtime so the hero number takes the room that's left and never collides with other content.
- **Money from figures the user adds.** Income, commitments, bills handled and renewals are computed from entered figures and saved monthly calculations, with the working shown. When a user has no saved manager figures, the Money chapter falls back to payments on the timeline.
- **Multi-domain architecture.** Life and Money for everyone; Home and Business as optional modes over the same timeline.
- **Privacy by design.** Availability links upload only busy and free times, never titles, places or people. Links are single-use, expire after seven days, and are protected by an owner key for edits and revocation. Group links let several people mark the times that work.
- **A website made of small living demos.** Each section demonstrates the product instead of describing it: typed capture, a month of money that totals as items land, a home whose admin arrives one item at a time, a recap that builds itself. Motion starts when a section enters the screen, pauses when it leaves, and stops for reduced motion.
- **CI/CD.** Pull requests run lint, type check and build. A push to `main` deploys to Vercel only if every check passes (`needs: ci`), using the Vercel CLI (`pull`, `build --prod`, `deploy --prebuilt`) with credentials in GitHub secrets. Vercel's own Git deploys are off, so the pipeline is the only route to production.

## Architecture

![Architecture](docs/architecture.png)

## API flow: sharing availability without sharing your life

![API flow](docs/api-flow.png)

## Data model

![Data model](docs/data-model.png)

## Status and roadmap

The website is live and the waitlist is open. The iPhone app is in pre-launch development. Still to come: server-side persistence for shared links, real email and text delivery, billing, direct Google and Microsoft calendar connections, a yearly Wrapped built on the same chapter model, and a richer share sheet with direct Instagram Stories support.

---

© 2026 NUO LIFE · Powered by NUO Tech
