# Competitive Analysis & Journey Map

> **Module 2 · Lab 2 — ★ Deliverable 2.** Repo file `02-discovery/competitive-and-journey.md` — part of your submission.
> Do the lab in the **Module 2 · Exercise 2 Guide** (linked from the Module 2 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Competitive Analysis & Journey Map** slide of your Module 6 final deck. Builds on your `ai-synthesis.md` and your Module 1 `problem-hook.md`.

## Responses

- **Role, who are you solving for?:** Frontline Driver. A delivery driver on a daily route, often handling packages in bad weather with one hand free.
- **Goal, what is this user ultimately trying to achieve?:** Mark each stop complete quickly and accurately so the route moves on without slowing the delivery.
- **Friction, the main barrier (moment of misery) stopping them:**
  - **Taps:** Marking a stop delivered takes three taps across three screens. Drivers in the rain, at a doorstep, with a package in hand have started texting their dispatcher instead (UXR-01; BUG-2055).
  - **Routing accuracy:** Optimized routes send drivers down closed roads and ignore loading docks and one-way streets. One driver overrides the route every day (UXR-05; BUG-2068).
  - **Availability:** The app crashes on longer routes and loses every remaining stop, which can cost twenty minutes while the office reads the list aloud (UXR-03; BUG-2031). In low-signal areas the stop list does not load, and the route is blank (UXR-06; BUG-2050).
- **External tools the user is forced to use:** Off-platform channels: SMS, driver knowledge and paper maps, phone calls.
- **The process, the 3–5 manual steps they take:**

  1. **Texting the dispatcher instead of marking a stop delivered.** Steps (from UXR-01):
     - Arrive at the doorstep in rain, holding a package.
     - Attempt the three-tap, three-screen completion flow.
     - Abandon the app and send a text to the dispatcher confirming the delivery.
     - Continue to the next stop.

  2. **Manually overriding optimized routes.** Steps (inferred; UXR-05 states the override happens daily but does not describe it):
     - Receive the optimized route.
     - Recognize a closed road, loading dock, or one-way restriction the optimizer does not know about.
     - Reroute by hand, relying on personal knowledge of the area.
     - Repeat this every day, since local overrides cannot be saved (BUG-2068).

  3. **Keeping a paper manifest and route screenshots.** Steps (from UXR-06 and UXR-12):
     - Each morning, screenshot the route while connected.
     - Carry the screenshot or a paper manifest into low-signal areas.
     - Work from the static copy, with no way to receive updates or record completion in the app.
     - Record completions on paper or by phone, then reconcile later.

  4. **The office reading the route aloud after a crash.** Steps (from UXR-03):
     - The app crashes mid-route and the remaining stops are lost.
     - The driver calls the office.
     - Someone at the office reads the stops from a screen.
     - The driver writes them down or memorizes them, with about twenty minutes lost.

- **Core frustration, where the process feels most "broken":**
  - **The route vanishes mid-shift (most severe).** The app crashes on longer routes and the remaining stops are gone. The driver has to call the office and wait while someone reads the list aloud, which costs about twenty minutes (UXR-03; BUG-2031, Critical). The data existed a moment earlier, so the loss feels arbitrary.
  - **The route is wrong and nothing says so.** A reassignment takes 8–15 minutes to reach the driver, with no push notification. The driver drives the old route, sometimes the wrong way, before finding out (UXR-02; BUG-2044, Critical). The app shows a confident, current-looking route that is stale.
  - **The photo appears to succeed and then doesn't.** About 35% of proof-of-delivery uploads fail on weak signal. The app gives no retry and no confirmation, so the driver cannot tell whether the delivery is recorded and retakes the photo, sometimes three times (UXR-07; BUG-2061, High).
- **The evidence, a quote or behavior from the research that proves this:**
  - **Mid-route crash: lost stops.** Quote (UXR-03, driver): "The app crashed mid-route and lost my remaining stops. I had to call the office to read them to me off a screen. Twenty minutes gone."
    - Observed (BUG-2031, Critical): crashes on Android 12/13 when the stop list exceeds about 40 stops. The remaining route is lost and must be reloaded from the server. Nothing is recovered from the device.
  - **Reassignments don't reach the driver.** Quote (UXR-02, dispatcher): "I reassign a route and the driver doesn't see it for ten, fifteen minutes. By then they've driven the wrong way. We keep a WhatsApp group as the real system."
    - Observed (BUG-2044, Critical): reassignments take 8–15 minutes to propagate to the driver app. No push notification is sent on a route change. Drivers act on stale routes.
  - **Photo uploads fail without feedback.** Quote (UXR-07, warehouse lead): "Proof-of-delivery photos take forever to upload and half fail. Drivers don't know if it worked, so they retake three times."
    - Observed (BUG-2061, High): about 35% of uploads fail on weak signal. There is no retry queue. There is no success confirmation, so the driver cannot tell whether the upload worked.
- **Journey map, a shareable link or the map file you committed:** [Future-state Frontline Driver journey](future-state-journey.svg)
