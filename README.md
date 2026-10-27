# E-CYCLE — Give Electronics a Second Life

Premium browser-local React + TypeScript e-waste collection, reuse and repair demo.

## Quick start

Prerequisites: Node.js 20+ and npm, with an internet connection for initial dependency installation.

```bash
npm install --legacy-peer-deps
npm run dev
```

Open the Vite URL printed in the terminal (usually `http://localhost:5173`).

Production build:

```bash
npm run build
npm run preview
```

Deploy the `dist/` folder on a static host such as Vercel or Netlify. Configure single-page-app history fallback to `index.html` if your host requires it. A `vercel.json` is included.

## Implemented workflows

- Premium responsive landing page with 3D phone (React Three Fiber), orbiting service labels, and animated panels.
- Resident device registration, image upload, image capture from camera, record browsing/deletion.
- Optional real browser-side MobileNet recognition (downloads a model at first use). Falls back to manual classification if model is missing or the category is not confidently supported.
- Guided condition assessment and rule-based transparent repair/donate/recycle recommendation, with safety exception for swollen batteries.
- Device-category eligibility, provider capacity, location and specialization weighted matching with a scored shortlist.
- Auto-allocation to first-ranked eligible demo partner, request tracking and status history.
- Technician / donation / recycling partner role switch, acceptance, rejection, quotes, scheduling, progress and completion.
- Same-browser one-time handover codes, expiring QR references, verification and completion records.
- Administrator partner creation/editing, capability, locality, availability, capacity and reassignment.
- Charts and impact numbers computed from actual local records, not fabricated impact figures.
- IndexedDB images and scan audit entries, LocalStorage main records, downloadable JSON backup and import, demo reset.

## Demo walkthrough

1. On Home click **Scan my device**.
2. Upload a device photo. Optionally try image recognition; always verify manually.
3. Fill in the condition questionnaire. Continue to recommendation, then save and find partners.
4. Choose **Auto-allocate to best match**.
5. Open **Settings** and change role to **Repair Technician** or **Donation / Recycling Partner**.
6. In **Assigned Requests**, accept the request; schedule a pickup, mark it in progress.
7. Generate a local handover code from the request. Enter the code and confirm completion.
8. Change role to **Resident** and inspect the status and impact, or to **Administrator** to manage the partner list.

## Honest limitations

This is a **browser-only prototype**, with **no backend and no real identity authentication**. Data is isolated to the current browser profile. There are no real providers, live capacities, real pickups, environmental verification or cross-device communication. Partners in the seed directory are **fictional demo profiles**, not real verified businesses. Browser storage can be cleared by browser settings; export backups regularly.

The MobileNet model performs general image classification; it is **not a specialized e-waste diagnostic model** and may fail to identify electronics. Its confidence is not a condition assessment. Model download needs connectivity at least once (and may not work on restrictive hosts). There is always a manual option. 3D and browser features may work differently depending on device/browser. The main UI and stored records continue to work without a backend. The application is not a certified e-waste handling service.

## Project structure

`src/App.tsx` — application pages and interactions

`src/store.ts` — types, storage, recommendation/matching logic

`src/style.css` — responsive design system

`src/main.tsx` — React application entry

## Troubleshooting

If `npm install` fails due to peer dependency differences, run `npm install --legacy-peer-deps`. If camera access is unavailable, use localhost or HTTPS and allow browser permission. If optional AI classification fails, use the manual category selector. Browser photo data is saved to IndexedDB, which has varying storage quotas.
