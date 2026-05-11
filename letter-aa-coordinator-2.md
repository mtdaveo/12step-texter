# 12th Step Texter — Introduction for D11 CPC Chair

I wanted to share something I've been working on that I think could make a real difference in how District 11 handles 12th Step calls from treatment facilities.

---

## The Problem It Solves

Right now, when a patient at Riverstone or another facility asks to speak with someone from AA, a staff member has to pull up a group text thread on their personal phone, type out the patient's information, and hope their volunteer list is still current. It works — but it puts a lot of burden on facility staff who aren't part of AA, and there's no standard format, so messages often come through missing key information.

---

## What This App Does

It's a simple web form that lives on a phone. Here's the flow:

1. A QR code is posted at the nurses' station (or sent to the facility contact)
2. Staff scans it — a clean, simple form opens on their phone
3. They fill in: facility name, room number, patient name, age, any notes
4. They select Male or Female (this routes the request to the right volunteer list)
5. They check a box confirming the **patient personally requested** AA contact — this is required before the form will submit, and it can't be bypassed
6. They hit Send — their phone opens a pre-written group text to all current AA volunteers with all the patient info filled in automatically
7. They hit Send one more time — done

Upgrades from current system:

1.	Facility no longer needs to input and maintain A.A. volunteer phone numbers.  We control that list and those #s.  When someone joins or leaves the list, the coordinator updates it once and every future request automatically reflects the change — no calls to facilities, no outdated threads. (Facility must use QR code for each text)
2.	Facility no longer needs to create a text message with all the information we need.  They simply fill out 3-5 fields.  A text (with all information we need) is generated and distributed to all A.A. volunteers on the list.


The volunteers receive a clean, consistent message. They can see each other's replies in the thread and coordinate from there, exactly as they do now.

---

## What AA Coordinators Do

One person in the district sets up the volunteer lists (separate Men's and Women's lists) through a coordinator page. When volunteers join or leave, the coordinator updates the list and the facility's form automatically reflects the change. No phone calls to facilities, no chasing down old text threads.

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

## Where It Goes From Here

This is built and working. The next step is getting it in front of one facility — even just as a test — to see how staff respond to it. If it works in Billings, it could roll out across Area 40 for any district that wants it.

I think this is worth bringing to the committee. Happy to demo it in person whenever you'd like.

~ Dave O.
Area 40 District 11.  Billings, MT,
mtdaveo@gmail.com.  406-670-6584.
