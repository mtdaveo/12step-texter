# 12th Step Texter — Introduction for Area 40 Webmaster

I've been working on a small web app that automates the 12th Step contact request process between treatment facilities and AA volunteers. I think it's ready to show you, and I'd love your take on where it goes from here.

---

## What It Does

When a patient at a hospital or detox facility requests a visit from AA, a staff member currently has to compose a group text manually and maintain a list of volunteer phone numbers on their personal device. This app replaces that friction with a structured form that builds and sends the message automatically.

**There are two sides:**

**AA Coordinator, probably someone on CPC Committee (admin)**
Configures the volunteer lists (separate Men's and Women's lists), sets the patient info fields the facility form will collect, and writes the outgoing message template using a token system. Also selects the District and City the configuration covers. Saves the config and generates a QR code for the facility.

**Facility Staff**
Scans the QR code on their phone. A form opens. They select Male or Female (routes to the correct volunteer list), fill in patient info (facility name, room, patient name, age, notes), confirm the patient personally requested AA contact (hard gate — can't submit without it), and hit Send. Their phone's native SMS app opens pre-populated with every volunteer's number and the fully formatted message. They hit Send. Done.

---

## What's Built

Three HTML files, zero dependencies, zero backend. Currently hosted on GitHub Pages:

- **Landing page:** https://mtdaveo.github.io/12step-texter/
- **Coordinator setup:** https://mtdaveo.github.io/12step-texter/sms-coordinator-setup-v10.html
- **Facility form:** https://mtdaveo.github.io/12step-texter/sms-facility-form-v5.html
- **Repository:** https://github.com/mtdaveo/12step-texter

The app is fully functional as a pilot. Token-based message builder, gender routing, required field validation, confirmation gate, QR code generation with share/download — all working.

---

## See It Live

You can see the full working app here:
https://mtdaveo.github.io/12step-texter/

This is the testing page for the app.  It only works as you play "both sides" (A.A. Coordinator & Facility) from your same browser window.

A.A. SIDE
1.	Set up A.A. volunteers (phone #s, names if you want).  One list for males, another for females.  This test is more visible if you have an additional phone #, but will work with your own.
2.	(If you want to edit) you can adjust text message that the Facility will generate via text/tokens in the Text Message Template.
3.	Hit SAVE CONFIGURATION at bottom right.
4.	Hit GENERATE QR CODE at bottom left.  (This is for testing purposes only.  Eventually, this will be a fixed QR code linking to : .../billings, etc.)

FACILITY SIDE
1.	On your mobile phone, scan the QR code generated above.  This opens up a form for the Facility to fill out.
2.	Fill out the form for a sample patient.  
3.	Hit SEND REQUEST TO AA VOLUNTEERS.

You should receive a text to the phone #s you provided on A.A. SIDE regarding the patient you created on FACILITY SIDE.

---

## The Wall We've Hit

GitHub Pages is static hosting. The coordinator config is currently encoded directly into the QR code URL — which means every time the volunteer list changes, a new QR code needs to be generated and reshared with the facility.

For a pilot with one facility, that's manageable. For broader deployment across Area 40, it isn't. What we really need:

- `aa-montana.org/12step/billings` — facility-facing form, reads current config from server
- `aa-montana.org/12step/billings-admin` — coordinator setup, writes config to server

When the coordinator updates the volunteer list and saves, the facility page reflects it immediately. The QR code pointing to `/billings` never changes. Print it once, laminate it, done.

---

## What That Requires on Your End

Essentially just a place to store and serve a JSON config object per city. The simplest possible implementation — a key/value store, one record per city. The coordinator setup page POSTs to it on save; the facility form GETs from it on load.

If that fits cleanly into how Area 40's site is already structured, I'd love to talk through it. If not, there are zero-infrastructure options (Firebase Firestore, JSONBin) that would let both pages stay on GitHub Pages while still sharing a live config.

Either way, the HTML is a complete functional specification. The logic, validation, token system, and message building are all done. The only open question is where the config lives.

Happy to walk you through it whenever works for you.

~ Dave O.
Area 40 District 11.  Billings, MT,
mtdaveo@gmail.com.  406-670-6584.