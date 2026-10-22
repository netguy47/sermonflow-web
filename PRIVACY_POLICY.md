# Privacy Policy — Sermon Flow

**Effective date: 22 October 2026**

**Published by:** `TODO-USER — insert the full legal name of the entity that publishes this app` (the "Company")
**Governing jurisdiction:** `TODO-USER — insert the governing law jurisdiction, e.g. "the laws of the State of X, without regard to its conflict of law provisions"`
**Contact address for privacy requests:** `TODO-USER — insert a monitored email address, e.g. privacy@yourdomain.com`
**Support address:** `TODO-USER — insert a monitored support email address`
**App:** Sermon Flow for iOS (bundle identifier `com.donwoods.Sermon-Flow`), and the Sermon Flow Home Screen widget.

> **Before publishing:** replace every `TODO-USER` marker. Apple rejects a submission whose privacy
> policy URL does not resolve, and a policy naming no responsible entity is not a publishable
> document. No other change is required — the text below already describes the app as it is built.

---

## 1. Summary

Sermon Flow is a note-taking app for people who write sermons. It stores the sermon notes you
write, on your behalf, so that they are available on your devices. It also offers an optional
AI-assisted drafting tool that helps you start a sermon outline. That is the whole of the data
relationship.

**In short:**

- We do **not** collect personal information.
- We do **not** use your data for tracking.
- We do **not** sell or rent your data to anyone.
- We do **not** use third-party analytics or advertising, and the app contains no advertising SDKs.
- We do **not** ask you to create an account, and there is no login screen, email address, or password.
- The AI drafting feature is optional and off until you ask for it. Scripture text is bundled with the app; only the short text you type into the Create tab is ever sent to an AI provider.

## 2. Who We Are

Sermon Flow is published by `TODO-USER — legal entity name`, a `TODO-USER — entity type, e.g. sole proprietorship / limited company`
registered in `TODO-USER — jurisdiction of registration` ("Sermon Flow", "we", "us"). Our contact
details are at the end of this policy. If you are in the EEA or the UK, `TODO-USER — insert the name of
the EU/UK representative if one is appointed, or delete this sentence if none is required`.

## 3. What the App Does and What It Stores

Sermon Flow lets you write, organise, search and read your own sermon notes. It detects scripture
references in your text and shows the passage from a Bible translation bundled inside the app. It can
also show your most recent note on your Home Screen widget. Separately, the Create tab can ask an AI
provider to draft a sermon outline from a passage, topic and instructions you type — see Section 4.

To do that, the app stores the following:

| What | Where it lives | Why |
|---|---|---|
| The sermon notes you create — a title, the body text, the date the note was created, and whether you flagged it as a "Life Application" | Cloud Firestore (Google Cloud), under an anonymous, device-scoped user ID | To save your notes, sync them across your devices, and display them back to you |
| An anonymous, device-scoped account identifier | Firebase Authentication (anonymous sign-in) | So that Firestore can scope your notes to you without an email address, password, or name |
| The most recent note (title, body text, date, and the Life Application flag) | A shared app-group container on your device, for the widget to read | So the widget can display it without a network request |
| A single setting recording whether you have seen the in-app welcome message | On-device preferences (UserDefaults) | So the message is not shown twice |
| Your notification permission choice, and any Monday reminders you have switched on | Managed by iOS, on your device | So the app can schedule reminders you have allowed |

Your sermon notes are written by you. The app does not generate, infer, or enrich your notes with any
third-party content, and it never sends your note text to an AI provider. The AI drafting feature
operates only on the separate text you type into the Create tab, and it never reads your notes.

## 4. AI-Assisted Sermon Drafting (optional)

The Create tab can draft a sermon outline for you. This feature is optional: everything else in the
app — writing notes, saving them, searching, organising, and the widget — works normally whether or
not you use it, and whether or not the AI service is available.

### Who handles the request

When you tap **Generate Outline**, the app first shows a disclosure sheet naming the provider. The
request goes to **our own drafting service running on Google Cloud (Firebase Cloud Functions)**, and
that service calls **Google Gemini** through the Google AI API. The provider's access credential is
held in Google Cloud's secret manager and is never contained in, or reachable from, the app that is
distributed through the App Store.

Before you submit, the app tells you which provider will handle the request and exactly what will be
transmitted.

### Exactly what is sent

Only the three fields you type in the Create tab are sent:

- the **passage** you entered,
- the **topic** you entered,
- the **instructions** you entered.

Nothing else is transmitted. Specifically, the app does **not** send your sermon notes, your
anonymous account identifier, any email address, any other Firestore content, your device
information, your name, or your payment information. The drafting service rejects any request
containing additional fields, so this limit is enforced on the server and not only in the app.

### How the provider processes it

The text you submitted is transmitted to Google Gemini, which processes it under Google's own terms
and privacy policy (https://policies.google.com/privacy). We do not use your submitted text to train
our own models, we do not add it to your notes automatically, and we do not sell it. The draft comes
back to the app for you to read.

### You can avoid sending anything

You choose whether to use the feature. Nothing is sent unless you tap Generate Outline and confirm the
disclosure sheet. If you would rather not use AI drafting at all, simply do not use the Create tab's
Generate button — no text leaves your device, and the rest of the app is unaffected.

### The output is a draft, not Scripture

Every AI-generated outline is labelled **"AI-generated draft—review Scripture references and
theological claims."** The outline is a starting point produced by a machine. It is not Scripture,
it is not a quotation, and it may be inaccurate. Verify every Scripture reference and every
theological claim against the Bible and your own sources before you preach it. The drafting service
instructs the model not to quote Scripture text and not to present any wording as the words of
Scripture, and the app adds no quotations, citations or scholarly sources of its own — but that is
a prompt-level instruction, not a guarantee, and no automated check can confirm every reference in
free-form text. You should not present any part of the draft as a quotation without checking it
yourself.

### If the service is unavailable

If the drafting service is unreachable, unconfigured, or declines the request, the app says so
plainly and shows no outline at all. It never substitutes a sample or invented outline. Your notes
and the rest of the app continue to work.

## 5. Data We Do Not Collect

We do not collect, request, or receive:

- Your name, email address, phone number, postal address, or any other contact details
- A username, password, or any credential you set
- Photos, videos, contacts, calendar events, health data, location data, or microphone audio
- Advertising identifiers, including the IDFA. The app does not access the advertising identifier and does not display the App Tracking Transparency prompt
- Browsing history, keystroke logs, or diagnostic data about your device

## 6. Anonymous Authentication, and Why Your Notes Are Private

The app signs you in to Firebase using **anonymous authentication**. When the app first runs, it
creates a random, non-identifying account tied to this installation and uses that account as the
key under which your notes are stored. No identity information is attached to it, and there is no
account screen, sign-up, or sign-in anywhere in the app.

The practical consequences, stated plainly:

- Your notes are stored against a randomly generated identifier, not against you as a person.
- Your notes are not visible to other users of the app, and the app has no feature for sharing notes with other users.
- We do not have a name, an email address, or a phone number against which to identify the owner of a set of notes, and we do not ask you for one.
- Because the identifier is anonymous and device-scoped, uninstalling the app or deleting it from your device means we may have no way to associate those notes with you. See Section 10 (Data Rights).

### How your notes are kept separate from everyone else's

The app's Firestore database enforces the separation on the server, not only in the app. Every
note document records the anonymous account identifier that owns it, and the database's security
rules allow a request only when the identifier on the request matches the identifier stored on the
document. The rules also require that a query name the identifier being read — the app's own
note list is filtered on it — so a request that tries to list every note in the database is
rejected by the server rather than filtered afterwards. A signed-out request is rejected outright.

The practical effect: a note written on one installation is not readable, listable, editable or
deletable from any other installation, and the app itself never requests notes it does not own.
This is enforced by the database, so it holds even if the app is modified or a bug is introduced.

## 7. Local Notifications

The app asks for permission to send you notifications the first time it launches. This is a
request for the standard iOS alert, sound, and badge permission, handled entirely by iOS on your
device. The app does not use a remote push service: it has no push-notification backend and does
not receive push messages from us or from anyone else. If you grant the permission, the app can
schedule local reminders on your device. A **Monday Recall** reminder, which you switch on
individually for a note, repeats every Monday at 9:00 AM local time on that device. You can switch
it off again on the same note, and deleting the note removes its reminder as well, so a reminder
never outlives the note it refers to. Reminders carry the note's title and the opening of its body
text, on your device only. You can decline the prompt, change your mind later in iOS Settings →
Notifications → Sermon Flow, and turn individual reminder types off. Declining the prompt does not
reduce any feature of the app; it only stops reminders.

## 8. Subscriptions and Purchases

Pro features are sold as auto-renewing subscriptions through the App Store. The purchase is
completed by Apple using Apple's own payment interface. We do not receive or store your card
details, your billing address, or your Apple ID password. We receive only the information Apple
provides about a completed transaction, such as the product purchased and a pseudonymised
transaction identifier, so that we can confirm whether your subscription is active. Refunds,
billing disputes, and subscription cancellation are handled by Apple; see the Terms of Service.

If you move to a new device or reinstall the app, you can restore your subscription without
purchasing again: **Settings → Restore Purchases**, or the same button on the in-app paywall,
asks the App Store to re-deliver your receipts for your Apple Account. The restore is performed
entirely by Apple and iOS; nothing about your subscription is sent to us beyond the same
entitlement information described above.

## 9. Third-Party Services

The app uses the following third-party services, and no other:

**Firebase (Google LLC)** — for anonymous authentication, for storing and syncing your notes, and as
the hosting platform for the AI drafting service described in Section 4. The Firebase project
identifier is `sermonflow-1b949`, and the Firestore database used is the project's Standard
`(default)` database. Firebase is a Google product. Your notes are therefore processed on Google
infrastructure, and Google's privacy policy applies to that processing:
https://policies.google.com/privacy

**Google Gemini, via the Google AI API** — used only when you ask for an AI draft, and only for the
three fields you type in the Create tab (Section 4). The provider processes that text under Google's
own terms and privacy policy: https://policies.google.com/privacy

We do not use Firebase Analytics, Firebase Crashlytics, Firebase Cloud Messaging, Firebase Remote
Config, Google Analytics, or any advertising network. The app contains no third-party analytics SDK
and no advertising SDK, and it requests no advertising identifier.

The app also links, in Settings → Scripture Credits, to the World English Bible website
(https://worldenglish.bible). Following that link takes you to a third-party site governed by that
site's own privacy policy. We do not receive any information from your visit.

## 10. Data Rights

Depending on where you live, you may have rights to access, correct, export, or delete the
personal data we hold about you, and to object to or restrict certain processing.

In practice, for this app:

- **Access and export.** Your notes are yours and you can read them, copy them, and export them at any time from the app itself — the note list shows the full text of every note. Because we hold no identity information for you, we can only answer an access request by working from the anonymous account identifier, and cannot map that identifier to a person.
- **Correction.** Edit or update a note at any time by opening it from the timeline and saving your changes.
- **Deletion.** You can delete any note yourself, at any time, from the app: open the note and choose **Delete Note**, or swipe the note in the timeline and choose **Delete**. This removes the note from cloud storage and from this device immediately, including when the app is on the free tier and the five-note limit is reached — the limit restricts new notes, never deletion. Deleting a note also removes any Monday reminder attached to it. If you want your remaining notes deleted from cloud storage in bulk, email us at `TODO-USER — privacy contact address` from the device on which the notes were created, with the anonymous account identifier so we can find the right records, and we will delete them. We respond to verified deletion requests within a reasonable period and in any case within the period required by applicable law. If you simply delete the app, we have no way to identify your notes, because we deliberately do not collect information that would let us do so. If you would like deletion as a matter of routine rather than by request, we recommend exporting anything you want to keep before uninstalling.
- **Consent and withdrawal.** Where we rely on consent (for example, notification permission, or your choice to use the AI drafting feature), you can withdraw it at any time in iOS Settings, or simply by not using the drafting feature.
- **Complaints.** If you are unhappy with how we have handled your data, you can complain to us at the contact address below, and you may also complain to your local data protection authority.

This policy does not apply to data held by Apple or Google. Requests concerning your App Store
account or your Firebase account data should be directed to Apple or Google respectively.

## 11. Data Retention

Your notes are retained in cloud storage for as long as you keep using the app, and until you
request their deletion or your anonymous account is removed by Google. On-device data (the shared
app-group copy of your most recent note, and the app's local settings) is removed when you delete
the app, and the shared copy of a note is also removed as soon as you delete that note in the app.
Notification permission state and any scheduled reminders are managed by iOS on your device. Text
you send to the AI drafting service is not retained by us beyond generating and returning your
draft; any retention by the AI provider is governed by that provider's own terms.

## 12. Children's Privacy

Sermon Flow is intended for adults, including pastors, preachers, ministry staff, and students of
religion preparing sermons, who are ordinarily 18 or older. The app is **not directed at children
under 13**, and we do not knowingly collect personal information from children under 13.

If you are a parent or guardian and you believe a child under 13 has created notes using this app,
contact us at `TODO-USER — privacy contact address` and we will delete those notes. Because
authentication is anonymous and we do not collect identifying information, we can act on such a
request once it is verified from the device in question.

The app's own content — a public-domain Bible translation, a note editor, an optional AI drafting
tool, and a widget — contains no material directed at children and no mechanism for them to identify
themselves to us.

## 13. Security

Your notes are transmitted over encrypted connections and stored by our cloud provider under an
anonymous account identifier that carries no personal information. The app is distributed through the
App Store, and Apple's platform security, including Keychain storage and data protection, applies
to the credentials and tokens it holds on your device. The credential used to reach the AI provider
is held on our server in Google Cloud's secret manager and is never shipped inside the app. No system
is perfectly secure, and we cannot guarantee absolute security; if a breach affecting your data
occurs and is likely to cause you harm, we will notify you and the relevant authority as the law
requires.

## 14. International Transfers

Your notes are stored by Google on infrastructure that may be located outside your country, including
in the United States. Where your law requires a safeguard for such transfers, we rely on the
transfer mechanisms that Google and Apple provide under their respective terms, including standard
contractual clauses where applicable.

## 15. Changes to This Policy

We may update this policy as the app changes or as the law requires. The effective date at the top
of this page always shows the version in force. If a change materially affects how we handle
information, we will notify you in the app before the change takes effect or, where appropriate, by
email. Continued use of the app after a change means you accept the updated policy.

## 16. Contact Us

- **Privacy questions and data rights requests:** `TODO-USER — privacy contact email address`
- **Support:** `TODO-USER — support email address`
- **Postal address:** `TODO-USER — postal address of the publishing entity`
- **Effective date:** 22 October 2026

Sermon Flow is published by `TODO-USER — legal entity name`, governed by the laws of
`TODO-USER — jurisdiction`.
