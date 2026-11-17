# Best VPS Provider: What You Should Pay, Whether Managed Is Worth It, and Which Plan Fits a Blog, a Store or a Self-Hosted AI Stack

Most people shopping for a VPS should budget **$20 to $100 a month**, and the plan they end up needing depends on a decision they usually make last: managed or self-managed. The $2.50 and $4 tiers that show up at the top of every comparison carry 512 MB of RAM, which is enough for a test instance and very little else.

Below that mainstream range sits a different market. RackNerd sells yearly KVM specials in it, with an entry box around **$22 a year**, unmanaged, full root, on a 1 Gbps port. That is roughly $1.83 a month, less than half what a 512 MB droplet costs over twelve months. What you give up for it is the whole point of this article.

Here is what each price band actually buys, how to size RAM to a real workload, which fees only appear at checkout, and where the cheap yearly model stops being the right answer.

> **Short answer for most readers:** if you can run a Linux server yourself and your workload is a VPN, one small site, or a single self-hosted app, RackNerd's entry KVM special at about $21.99 a year covers it. If you want someone else to patch the OS and answer the phone, budget $20 to $100 a month for a managed plan.
>
> 👉 [See the current RackNerd VPS specials](https://bit.ly/RacKnerd)

## RackNerd's VPS lineup and what each tier is for

RackNerd doesn't publish a fixed monthly ladder the way DigitalOcean or Vultr do. It sells promotional "specials" that rotate, all on the same platform: KVM virtualization, full root SSH, the ctrl control panel, a 1 Gbps port, and a choice of CentOS, Rocky Linux, AlmaLinux, Fedora, Debian or Ubuntu. Custom ISO installs go through a support ticket, and ctrl can reinstall the OS later from the panel.

| Plan tier | What you get | Price and term | Best for | Order |
| --- | --- | --- | --- | --- |
| Entry KVM special (1 GB class) | KVM, full root SSH, ctrl panel, 1 Gbps port, six Linux distros | ~$21.99/year, 3 TB transfer | A VPN, one small site, a single light app | [Check the entry special](https://bit.ly/RacKnerd) |
| 2 GB KVM special | Same platform, twice the RAM | ~$35.99/year on promotion | n8n, Coolify, Docker, two or three small sites | [See the 2 GB tier](https://bit.ly/RacKnerd) |
| 4 GB tier | The minimum for the Ollama, LibreChat, AnythingLLM and Hermes Agent one-click installs | Priced on the live specials list | Self-hosted LLM front ends, busier sites | [View the 4 GB options](https://bit.ly/RacKnerd) |
| 8 GB tier | The minimum for the OpenClaw one-click install | Priced on the live specials list | AI agent workloads, heavier container stacks | [View the 8 GB options](https://bit.ly/RacKnerd) |

Two caveats on the table. The specials rotate, so names, RAM and prices change month to month and the live list is the only source of truth. The two figures above are what was advertised when this was written.

## Size the box to the workload, not to the price

A small business site runs comfortably on **2 vCPU and 4 GB**. Several WordPress sites on one box want **4 vCPU and 8 GB**, because plugins, staging copies, caching layers and simultaneous admin logins all compete for the same memory. An ecommerce store should start at **4 or more vCPU and at least 8 GB**, since catalog size, concurrent shoppers, search and checkout all load the server at once. A SaaS app depends on its database and background jobs, so there's no single number.

Self-hosted AI tools have their own floors, and RackNerd states them on the specials page: OpenClaw wants 8 GB of RAM, while Ollama, LibreChat, AnythingLLM and Hermes Agent want at least 4 GB. n8n and Coolify run fine from 2 GB. That single detail disqualifies the cheapest tier for most of the people who are actually excited about it.

If you're running a personal WireGuard endpoint plus a couple of nginx sites, the numbers are much smaller. A reviewer running exactly that on a 1 GB RackNerd plan measured about **230 MB of RAM in use** with the load average sitting at 0.00. That's the honest case for buying small: a static site or a VPN genuinely doesn't need more.

## The fees that show up after you've picked a plan

Control panels are the most common hidden line item. IONOS sells Plesk separately rather than bundling it. ScalaHosting gives away its own SPanel but charges extra for cPanel. Neither is a trick, but both change the real monthly cost of a plan that looked cheaper on the comparison page.

Backups, extra IPs and traffic overage behave the same way. Some hosts include them; others bill per item. A backup stored only on the primary server isn't a backup, and a plan with no published uptime commitment gives you nothing to point at when the box goes down.

Prices also move. Hetzner repriced its CX line in June 2026, pushing entry plans from the sub-€4 figure that older reviews still quote to roughly **€6.49–6.99 a month**. DigitalOcean switched Droplets to per-second billing in January 2026. Any comparison article older than a year is quoting a market that no longer exists, which is why the renewal rate on your specific plan matters more than the introductory headline.

Three things to confirm before you pay:

1. What the price becomes at renewal, and how long the discounted term runs.
2. Whether the panel, backups and extra IPs are bundled or billed separately.
3. Whether "managed" is defined anywhere in writing, or just implied by the word.

👉 [Compare the RackNerd specials and the term they bill on](https://bit.ly/RacKnerd)

## What running a RackNerd VPS is actually like

Every RackNerd VPS special is **unmanaged**: you get root and you own the operating system, the firewall and the updates. The ctrl panel handles the routine chores, including reboots, OS reinstalls, an HTML5 VNC console for recovery, root password resets, an inbound firewall, plan upgrades, and one-click installs for Docker with Portainer, WordPress stacks, n8n, Coolify, Ollama, OpenClaw and a handful of others. Support is staffed 24/7, but "unmanaged" means the OS is yours.

Two details matter more than they sound. IPv6 is available on request in Los Angeles and France, up to 100 addresses per server. And one long-term customer notes that port 25 isn't blocked, which is unusual among providers and decides the question if you plan to send mail from the box.

Reviews are mixed in the way real reviews are. A customer on a Black Friday plan since 2023 says the server has never gone down. A team running production there since early 2024 lists support fixing rDNS and PTR records, SMTP banners, MariaDB external connections, failing OS updates, a Docker container on port 443 and an Ubuntu 24.04 upgrade, several of which sit well past where most hosts stop and cite the unmanaged boundary. One reviewer had a cancellation request for the wrong server mishandled and got a generic template back instead of a straight answer.

On renewal pricing, a customer who bought a 2024 promotional plan reports it still renews at the original price even though the deal itself is gone. That's one data point, not a policy, so read the renewal terms on whatever you order.

## How RackNerd compares to the mainstream options

The rest of this market splits into developer clouds and managed hosts. Both are worth paying for when they match your situation.

| Provider | Verified entry pricing | Entry specs | Where it wins |
| --- | --- | --- | --- |
| DigitalOcean | $4/month; 2 vCPU/4 GB around $24/month | 512 MB, 1 vCPU | Documentation depth and a large one-click app marketplace; per-second billing since January 2026 |
| Vultr | From $2.50/month | 512 MB | Over 30 data center locations, the widest regional spread here |
| Hetzner | ~€6.49–6.99/month after the June 2026 repricing | 4 GB | Price-to-performance in the EU, 20 TB of included traffic; CX/CAX tiers are EU-only |
| Contabo | ~€4.50/month | 8 GB | RAM per euro; a separate Storage VPS line for large disks |
| Hostinger | Roughly $5–$6.50/month depending on term and source | 4 GB | 74 one-click installs, free domain, self-managed with full root |
| IONOS | Low entry pricing, unlimited traffic | 1 GB | Cheap and flexible plan switching; Plesk costs extra |
| ScalaHosting | $29.95/month on a three-year term (older data) | 2 cores, 4 GB | Managed VPS with free SPanel and off-site backups; cPanel costs extra |
| Liquid Web | Self-managed cloud VPS from $5/month (older data); managed $14.75–$42.25/month on a two-year commitment | 1 GB | 100% power and network uptime guarantee, 59-second support response target |
| DreamHost | Plan-dependent | Varies | Unlimited monthly transfer on every VPS tier, WordPress-optimized |
| Hostwinds | Plan-dependent | Varies | Managed or unmanaged, Linux or Windows, RAM up to 96 GB |

A few notes on reading that table. The Hostinger figure has been quoted at both $4.99 on a two-year term and around $6.49 more recently, so treat it as a range rather than a number. The ScalaHosting and Liquid Web prices come from earlier coverage and may have moved. Liquid Web's own comparison content puts its brand at the top, which is what you'd expect from a vendor publishing a ranking of its competitors; the selection framework is sound, the ordering isn't neutral.

Where each one genuinely fits: pick DigitalOcean if you want the best documentation and prebuilt images and don't mind paying for polish. Vultr if latency to a specific region drives the decision. Hetzner if your users are in the EU and you want the most CPU per euro. Contabo if RAM is the binding constraint. ScalaHosting if you want managed Linux with a free panel. Liquid Web or DreamHost if you'd rather not touch the OS at all.

## Which one you should actually buy

Match the rule to your situation:

- **A VPN, one small site, or a single app you maintain yourself** → RackNerd's entry special at about $21.99 a year. Nothing in the mainstream clouds beats that on price for this workload.
- **n8n, Coolify, or a few small Docker services** → the 2 GB tier at roughly $35.99 a year, not the entry box.
- **Any self-hosted LLM tool** → 4 GB minimum, 8 GB for OpenClaw. The cheap tiers aren't an option here regardless of provider.
- **A store or anything customer-facing that can't go down** → managed hosting in the $20–$100 a month band, or a developer cloud plus someone on your team who owns the server.
- **You don't want to patch a kernel at 11pm** → managed, full stop. The savings from unmanaged hosting disappear the first time an unpatched box takes your site offline.

Before you order anything: confirm the renewal price and the term it applies to, check whether backups leave the primary server, and find out whether the control panel is included or a separate purchase. Those three answers separate a cheap plan from an expensive mistake.

👉 [Start with the RackNerd entry VPS special](https://bit.ly/RacKnerd)
