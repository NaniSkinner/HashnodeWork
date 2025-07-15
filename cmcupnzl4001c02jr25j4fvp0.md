---
title: "Building ChainCal: My Journey from Curiosity to a Hackathon-Ready On‑Chain Calendar"
seoTitle: "Building ChainCal: From Idea to Hackathon Star"
seoDescription: "Explore the journey of developing ChainCal, an on-chain calendar tool for smart-contract events with insights on successes and learning experiences"
datePublished: Tue Jul 08 2025 15:54:53 GMT+0000 (Coordinated Universal Time)
cuid: cmcupnzl4001c02jr25j4fvp0
slug: building-chaincal-my-journey-from-curiosity-to-a-hackathon-ready-onchain-calendar
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1751989909210/34fe7ad1-c7e0-4c00-98fa-ff3209cc1490.png
tags: web3, alchemy, techlearning, vibe-coding

---

There’s something oddly satisfying about combining two things I love—building with code and making everyday life feel a bit more intentional. Over a whirlwind week, I built **ChainCal**, a tool that turns smart‑contract events into calendar reminders, email alerts, and even a Farcaster mini‑app (Frame). Here’s how it went—warts and all.

### **What I Built (and Why It Matters)**

By the end of the sprint, ChainCal had:

* A **Listener service** catching Alchemy webhooks, parsing events, and storing them in PostgreSQL using **Drizzle ORM**.
    
* A **Scheduler** hanging out in Redis, popping reminder jobs when they’re due, and sending emails via **Alchemy Notify**.
    
* A **Web dashboard** built in SvelteKit where you can visually add events or export them as an .ics file.
    

In practice, it meant: I can subscribe to a DAO vote closing or a vesting unlock and get an email just when it matters.

### **What Worked**

* **Fast webhook → DB → queue pipeline**: Events fired on-chain, hit our listener, saved in Postgres, queued in Redis—and the reminder popped *just* when expected (usually within 10 seconds).
    
* **Minimal infra, maximum effect**: With Alchemy + Redis and Postgres, I didn’t have to build email servers or complicated cron jobs. Team &gt; Tools.
    
* **Drizzle + TypeScript**: The schema-first, typed-as-you-go style meant cleaner migrations, safer queries, fewer runtime surprises.
    

### **What Didn’t Work: Farcaster MiniApp**

Now let’s talk about the part that humbled me:

**The Farcaster MiniApp integration… did not work.**

I followed the docs. I checked the examples. But somewhere between the manifest, signature verification, and URL structure—it just wasn’t clicking. I watched others get theirs working, so I knew the problem wasn’t the tool. It was me.

And maybe the fact that I was alone. No one to rubber-duck the issue with, no pair programming, no one to say, “Wait… did you check the frame payload?” Just me and my slightly-too-confident AI co-pilot.

I ended up shelving the MiniApp part and focusing on the core logic. I’ll return to the Frame side again soon, but this time with more patience—and maybe a buddy

### **Lessons Learned (Fast)**

* **AI needs direction.** My tools are great at generating code, but they don’t know the architecture unless I guide them. Vibe coding needs a map.
    
* **Go slow to go fast.** Every time I rushed past a setup step or skimmed a doc, I paid for it later.
    
* **Shipping isn’t success—learning is.** Even without the Frame, I built a working product that taught me a ton.
    

### **Final Reflection**

This hackathon reminded me why I’m here: to build in public, to learn from every bump, and to be radically honest about what it actually takes to become a better dev. ChainCal may have started with smart contracts, but it ended with smarter choices.

So if you’re on the same path—building, breaking, learning—know that you’re not alone. I’ll be here, sipping matcha, coding out loud, and reminding us all that the work is the reward.

👉 [@Check out the repo here](https://app.usemotion.com/web/pm/docs/0f6f5abf-789d-4d42-a773-0d26b7918057)

🧠 Follow along for more honest dev journeys on **Minds, Matcha, and Machines.**