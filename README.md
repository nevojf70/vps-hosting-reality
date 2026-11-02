# virtual private server hosting: what a $21.99/year plan actually gets you, and how to pick a cheap VPS without getting burned

Most people searching for virtual private server hosting want the same thing: a small slice of a server they fully control, with root access, a dedicated IP, and a price that doesn't double at renewal. The catch is that the VPS market prices the same hardware wildly differently, and the cheapest headline number often hides a long billing term or a renewal trap.

This article walks through the actual numbers. The centerpiece is RackNerd, a US-based unmanaged KVM VPS provider whose specials line starts at **$21.99 per year** and renews at the same price, compared against what bigger names like Hostinger, DigitalOcean, and Vultr charge for comparable plans. You'll also get the fine print that matters most with budget VPS: no refunds by default, no included backups, and support that covers hardware and network only.

> **Quick picks**
> - Just need a Linux box for a proxy, a bot, a small site, or SSH tunnels: RackNerd's **1 GB KVM VPS at $21.99/year** (1 vCPU, 20 GB SSD, 3 TB monthly transfer) is enough, and it renews at the same price.
> - Running n8n or Coolify: start at 2 GB ($35.99/year).
> - Self-hosting Ollama, AnythingLLM, or LibreChat: 4 GB minimum ($59.99/year).
> - 👉 [check current RackNerd VPS special pricing and locations](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397)

## What a KVM VPS plan actually includes

A KVM virtual private server is a fully isolated virtual machine on shared hardware. You get your own kernel, your own RAM allocation, full root access, and an IPv4 address nobody else uses. Unlike container-based "VPS" offerings, KVM lets you run your own kernel modules, custom ISOs, and pretty much any Linux distribution.

RackNerd's current specials page lists exactly five plans, all billed annually with full root access, 1 Gbps network port, 1 IPv4 address, and the ctrl control panel:

| Plan | vCPU / RAM | SSD | Transfer / mo | Price (yearly) | Order |
| --- | --- | --- | --- | --- | --- |
| 1 GB KVM VPS | 1 / 1 GB | 20 GB | 3 TB | $21.99 | [ Order](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397) |
| 2 GB KVM VPS | 2 / 2 GB | 35 GB | 5 TB | $35.99 | [ Order](https://my.racknerd.com/cart.php?a=add&pid=953&aff=11397) |
| 4 GB KVM VPS | 3 / 4 GB | 60 GB | 7 TB | $59.99 | [ Order](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397) |
| 6 GB KVM VPS | 6 / 6 GB | 100 GB | 12 TB | $89.99 | [ Order](https://my.racknerd.com/cart.php?a=add&pid=955&aff=11397) |
| 8 GB KVM VPS | 7 / 8 GB | 150 GB | 20 TB | $119.99 | [ Order](https://my.racknerd.com/cart.php?a=add&pid=956&aff=11397) |

Notice how the pricing scales. Going from 1 GB to 8 GB RAM costs roughly 5.5x, while the RAM increases eightfold and storage increases 7.5x. That's unusually gentle scaling for this market, which is why the mid-tier plans deserve a serious look rather than defaulting to the cheapest one.

RackNerd also sells a standard KVM line outside the specials page (512 MB at $26.99/year, annual billing only, with monthly billing available on larger tiers), plus a separate Windows VPS line with licenses included. For most readers the specials above are the better deal per dollar, so the rest of this article focuses there.

## The real cost over three years: renewal is where cheap VPS deals separate

The single most misunderstood number in VPS pricing is the renewal price. Promo rates from large hosts usually apply only to the first term, and the renewal rate can be double or triple what you paid.

Here's the contrast with real numbers. Hostinger's KVM 1 plan advertises $6.49/month, but that rate requires a 24-month prepayment of $155.76. It renews at $11.99/month for the same term. So year three alone costs $143.88, and the three-year total comes to about $299.64. RackNerd's 1 GB special is $21.99 in year one, $21.99 in year two, $21.99 in year three: **$65.97 total**, because the specials page states these plans are "lifetime recurring" and renew at the same rate as long as you keep the service.

Yes, Hostinger's plan includes more RAM (4 GB vs 1 GB), NVMe storage, weekly backups, and a malware scanner. It's a different product tier. The point is narrower: when you compare VPS hosting deals, divide the total three-year spend by what you actually use, and check the renewal price before the headline price. A $2.24/month figure you sometimes see on RackNerd's homepage is an annual-equivalent calculation, which is why it doesn't match any monthly plan page.

One more accounting detail: RackNerd's site displays prices in "$" without naming the currency or stating whether tax is added, so the final checkout total is the number to trust. There's no separate renewal price listed anywhere because there isn't one; it's the same number.

## The unmanaged fine print: refunds, backups, and what "support" means

Budget VPS hosting is almost always unmanaged, and RackNerd is no exception. But the specifics deserve more attention than most comparison articles give them, because they're the difference between a pleasant $22/year and a frustrating one.

**Support covers the infrastructure, nothing else.** RackNerd's terms say VPS services "are unmanaged by default," with best-effort support limited to "server hardware, power, network connectivity, and service availability." Explicitly excluded: software problems, operating system issues, coding, firewall configuration, server hardening, malware cleanup, and third-party application support. If you can't run `apt update` without a guide, factor in either managed hosting elsewhere or time spent reading documentation. Managed plans exist on request for an additional fee.

**Refunds are not guaranteed.** The terms state plainly: "Refunds are issued on a case-by-case basis since by default no refunds are provided once payment is received." There's no money-back guarantee and no trial. Account balances aren't refundable either. Because the specials are annual-only, you're committing for a year.

**There's a cancellation notice window.** Contract services require written notice through the client area at least 7 days before renewal, and your data is deleted immediately when a service is canceled. Mark your renewal date somewhere. Downgrades need 5 days' notice.

**No backups are included with VPS plans.** RackNerd's shared hosting includes daily JetBackup, but VPS, dedicated, and colocation customers are on their own. The company's own blog suggests rsyncing data to a second VPS. The control panel doesn't advertise snapshots or automated backups, so plan your backup routine from day one if your data matters.

There is an SLA, for what it's worth: 99.999% monthly network transit and power availability, with 2% of the monthly fee credited per hour of downtime, capped at 50%, claimed by email within 30 days. Scheduled maintenance of up to 180 minutes per month is excluded. A public status page tracks all 20 datacenters individually, which is more transparency than most budget hosts offer.

## Which plan fits your workload

Size the plan around what you're installing, not around the price ladder. RackNerd publishes minimum memory requirements for its one-click apps in the ctrl panel, and they map cleanly onto the plan tiers:

- **1 GB ($21.99/year)**: reverse proxy, WireGuard/OpenVPN endpoint, small static sites, Discord bots, cron jobs, learning Linux. AnythingLLM and Ollama are out of reach here; that's fine.
- **2 GB ($35.99/year)**: n8n workflow automation or Coolify self-hosting platform, both of which run comfortably from 2 GB. Also reasonable for a small WordPress install with the one-click AdminBolt or CyberPanel options.
- **4 GB ($59.99/year)**: the floor for Ollama, AnythingLLM, LibreChat, and Hermes Agent. If "run my own local LLM" is why you're shopping, this is your starting point, and 3 vCPUs with 7 TB of transfer leave room for a few side projects.
- **6 GB / 8 GB ($89.99 / $119.99/year)**: multiple services alongside each other, busier databases, or OpenClaw, which wants at least 8 GB.

The ctrl panel handles the basics without a separate management layer: reboot, OS reinstall (choose CentOS, Rocky Linux, AlmaLinux, Fedora, Debian, or Ubuntu at order time), an out-of-band HTML5 VNC console for recovery and custom ISO installs, inbound firewall rules, root password resets, and in-place upgrades. Custom ISOs go through a support ticket.

On locations: RackNerd operates roughly 20 datacenters across the US (Los Angeles, San Jose, Seattle, Dallas, Chicago, New York, Atlanta, Ashburn, and more), Canada (Montreal, Toronto), Europe (London, Amsterdam, Frankfurt, Strasbourg, Dublin), and Singapore. One quirk of promo plans is that available locations are often tied to the specific deal, and you pick the city in the order form, so check the dropdown before paying. If you need IPv6, up to 100 addresses are free on request in Los Angeles and France via a ticket after ordering.

If you've settled on the AI-workload tier, 👉 [the 4 GB KVM VPS at $59.99/year is the cheapest entry point for Ollama and AnythingLLM](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397).

## How the pricing compares with other budget VPS hosts

To put the numbers in context, here are currently published prices from providers in the same market segment. All are unmanaged plans on the Linux side:

| Provider, plan | Price | RAM | Storage | Transfer | Notable terms |
| --- | --- | --- | --- | --- | --- |
| RackNerd 1 GB special | $21.99/year | 1 GB | 20 GB SSD | 3 TB | Same price at renewal; annual only |
| InterServer 1 slice | $3/mo | 2 GB | 40 GB SSD | 2 TB | Monthly; no refund |
| Vultr 512 MB | $3.50/mo | 512 MB | 10 GB SSD | 0.5 TB | Hourly billing |
| DigitalOcean Basic 512 MB | $4/mo | 512 MB | 10 GB | 500 GB | Per-second billing |
| Hostwinds 1 GB unmanaged | $4.99/mo | 1 GB | 30 GB SSD | 1 TB | Hardware/network support only |
| OVHcloud VPS-1 | $5.35/mo | 4 GB | 40 GB NVMe | Unlimited | Daily backup included |
| Hostinger KVM 1 | $6.49/mo (24-mo term) | 4 GB | 50 GB NVMe | 4 TB | Weekly backups, API, renews $11.99/mo |

The honest read: hourly-billing clouds (Vultr, DigitalOcean) win when you need to spin servers up and down constantly, and their platform tooling is deep. OVHcloud and Hostinger include backups and broader support, which matters if you don't want to think about rsync. InterServer is a fair month-to-month alternative if you refuse annual commitments. RackNerd's edge is the annual price itself: $1.83/month-equivalent for a full gigabyte of RAM and 3 TB of transfer is several times cheaper than anything above, with the unusual bonus of a renewal price identical to the signup price.

What you trade away is covered in the fine print section above: unmanaged support, no included backups, case-by-case refunds.

## FAQ

**Is a $22/year VPS provider legitimate?**
RackNerd LLC is a Delaware-registered company with a California mailing address, and it has appeared on the Inc. 5000 list for three consecutive years (ranking #1506 nationally in 2024, #3036 in 2025, and #3693 in 2026). The service runs on a public status page covering all 20 datacenters, and the SLA terms are published. What it isn't is managed hosting; the low price exists precisely because everything above the hardware layer is your job.

**Can I run Windows on these plans?**
No. The specials are Linux-only (CentOS, Rocky Linux, AlmaLinux, Fedora, Debian, or Ubuntu). Windows Server is available on a separate product line with Ryzen hardware and NVMe storage, license included, priced separately.

**What happens when my annual plan expires?**
It renews at the same price you paid, per the lifetime recurring policy on the specials page. You need to give written notice at least 7 days before the renewal date if you want it to lapse, and data is deleted immediately on cancellation.

**Do I get a dedicated IP address?**
Every plan includes 1 IPv4 address. IPv6 is available free (up to 100 addresses) on request in the Los Angeles and France locations.

## Before you click order

Match the plan to the workload, not the price tag: 1 GB for proxies and small services, 2 GB for n8n or Coolify, 4 GB before touching Ollama or AnythingLLM. Check the location dropdown at checkout, since promo plans bind you to specific cities. And set a calendar reminder about a week before the renewal date, because cancellations need 7 days' written notice and there's no safety net of a refund after payment.

If that trade-off works for you, 👉 [grab the 1 GB KVM VPS special at $21.99/year before the pricing changes](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397) — deals at this tier do rotate, and the lifetime renewal rate only works in your favor if you lock it in while it's live.
