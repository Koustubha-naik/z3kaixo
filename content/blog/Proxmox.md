---
title: "How I Accidentally Became Addicted to Proxmox (And Why I Love It)"
description: "How a $200 ThinkPad became my 24/7 homelab beast running Proxmox, VMs, containers, dashboards, and more — all from my bedroom."
date: "2026-07-13"
featuredimage: "/img/prox.webp"
---

When I first installed Proxmox, all I wanted was to run one tiny VM. Just a Kali box. No big plans. No massive homelab dreams. Just a little space to play around and maybe try a few CTFs. But a few weeks later, I’m staring at the Proxmox dashboard like it's the freakin’ stock market, SSH’d into three different containers, and already thinking about buying more SSDs. What even happened?

It all started with my ThinkPad T480. Bought it for cybersec , reliable, kinda beat up — but still rocking an i7, 32 gigs of RAM, and a decent SSD ... got it around  $200. I wiped it clean, flashed the Proxmox ISO, and bam — the web interface came up like magic. No driver mess, no setup drama. Just smooth, nerdy satisfaction.

At first, I was naive. I thought Proxmox was just like VirtualBox with some extra spice. Boy, was I wrong. This wasn’t just virtualization — this was power. Real power. I was spinning up containers in seconds, cloning VMs like I was copying files, rolling back with snapshots like a damn time traveler. I felt like a wizard. 🔥

Sure, you can do this with VMs on VMware too — but this? This felt different. For real.

My first experiment? An Ubuntu LXC container with Nginx. Sounds basic, right? But when I opened the browser and saw the “Welcome to Nginx” page — from inside a container — running on my old ThinkPad? Bro, I was giddy. That was my first hit of homelab dopamine.

Then came the VMs — Kali Linux, Windows 10, Parrot OS… even Arch (which, let’s be honest, I broke in 10 minutes). The performance blew me away. I could run multiple VMs side-by-side without the machine even flinching.

Oh, and LXC? Still one of the coolest things I’ve discovered. Think of it as a lightweight, isolated Linux environment that shares the host’s kernel but runs its own user space — like a mini virtual machine without all the overhead. Pretty cool, right? Plus, it uses way less RAM, which was a huge win for me.

Things escalated fast. I started messing with file sharing, VLANs, remote access — all the good stuff. Before I knew it, I was knee-deep in network configs and system logs, loving every second of it.

I installed Pi-hole — boom, no more ads across my whole network. Suddenly, I couldn’t stand watching YouTube without it. Then came BookStack for notes. Jellyfin for media. One by one, I was turning my laptop into a Swiss Army server.

But of course, I hit snags. Storage ran out real quick. I had to dive into external SSDs, learn how to bind mount, format, partition, and deal with permissions like a real sysadmin. ZFS? ext4? LVM-thin? NFS? Yeah — I learned it all. For real. 💥

Networking... oh man. I once misconfigured a bridge and completely lost access to the web UI. I had to connect a physical monitor again (ew), boot into the terminal, and fix the whole mess like some 90s hacker. It was chaotic. It was fun. I kinda loved it. Painful, but fun 😂😂🔫

Then came the game changer — Cloudflared tunnels. I figured out how to expose Jellyfin, BookStack, and more to the internet — securely, with no port forwarding. Everything was encrypted, fast, and just worked. I could access my media and notes from literally anywhere.

My ThinkPad? It wasn’t a laptop anymore. It was a damn server.

Things got wild after I added GitHub Actions. One push to a repo and — boom — my new service was live. I was deploying stuff like a DevOps engineer... from a ThinkPad in my bedroom. In pajamas. At 3 AM. Absolute vibe.

And that’s when I knew it had gone too far: I started caring about uptime. Like, really caring. If my server shut down or even went to sleep, I’d panic. I disabled every power-saving feature. I even ripped out the battery because it was messing with the boot process.
Sleep mode? Nah. My server had work to do.

I became obsessed with dashboards. Grafana, Telegraf, InfluxDB — all just to see fancy CPU graphs. I’d literally sit there and watch RAM usage go up and down. For fun.

Automation became my next obsession. I wrote scripts to auto-update containers, fix file permissions, backup VMs, reboot services — all scheduled via cron like some mini production pipeline. I even built health check scripts that would ping me if something died. Proxmox was turning me into a monster. A happy one. But I wasn’t done. I kept adding more and more tools. FileBrowser gave me a slick file manager I could access from anywhere. No more USB drives. Just drag-and-drop straight to my server from my phone.

I set up Uptime Kuma. Now, if anything crashed — Pi-hole, Jellyfin, whatever — I’d get a Telegram ping. Like I was running a corporate server. I wasn’t. But it felt like I was. And I loved the rush.Then came the big one — Jellyfin. My own personal Netflix. I dumped in old movies, anime, hacking documentaries (don’t judge), and boom — I was streaming my own content, anywhere, anytime. Friends asked what streaming app I was using. I told them: me.BookStack became my knowledge base. Payloads, red team tricks, Wi-Fi exploits — all in one place, beautifully organized.

Docker? Yeah, got into that too. I started running stuff like FileBrowser, CTFd, and Kuma inside Docker... inside LXC... inside Proxmox. Layers on layers. I was building a lasagna of virtualization and loving every bite. Tailscale was next. Mesh VPN. I could access my homelab from college Wi-Fi, my phone, even my friend’s house. My network went with me everywhere.

Backups became an art. I wrote scripts to snapshot containers, clone VMs, rsync data to external drives — all on schedule. If something broke? Restore. If the restore broke? Restore the restore. I was unstoppable.

I started calling it “The Mothership.” Every device in my house — phone, laptop, TV — somehow connected back to that ThinkPad. If it wasn’t running, the whole network felt... incomplete.

Then I made a Homer Dashboard. All my tools in one click. My browser homepage was now a control panel. A friend saw it and asked, “Are you hacking NASA?” I said, “Nah bro, just running my ad blocker.”

Even basic stuff had to go through the server. Want to convert a video? I had a script. Check SSD health? Smartmontools container. Log monitoring? Logwatch and fail2ban. Wi-Fi attacks, payloads, Evil Twin lab? All stored and synced.

On bad days, I’d just SSH in and run htop. Watching processes move in real time was my therapy. I’m not even joking.

Proxmox didn’t just become part of my routine. It was the routine. I wasn’t just hosting things. I was the sysadmin, the dev, the user, the support team — all in one.

This wasn’t just a server. It was my lab. My playground. My therapy. My dojo. My Batcave.

If you’re even slightly curious about homelabs — just do it. Grab an old laptop. Install Proxmox. Break things. Fix them. Make it yours. One day, you’ll blink and realize your dusty ThinkPad is now a 24/7 powerhouse running 10 VMs, streaming movies, hosting notes, blocking ads, and quietly running your entire digital life.

Welcome to the madness. You’re gonna love it.