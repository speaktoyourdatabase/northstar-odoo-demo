**[Download Northstar](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases/latest/download/northstar-odoo20.zip)** | [Releases page](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases) | [Français](README.fr.md)

The green Code > Download ZIP button does not contain the database.

## Quick start

1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/) and start it.
2. Unzip the download into an empty folder, open a terminal in it and run `docker compose up`. When it says `Northstar is ready`, open <http://localhost:8069> and log in with `admin` / `admin`.

The details are below.

# Northstar: a fictional company for Odoo 20 Community

Northstar Office & Industrial Supply Inc. is a fictional US company in Columbus, Ohio: a B2B distributor of office, facility and light
industrial supplies with about 25 employees. It comes as a ready-to-run Odoo 20 Community database with 12 months of history, every app
connected to the others, and books that are right to the cent.

**Data until 10 November 2026, refreshed every week.** (History from 10 November 2025. Odoo 20.0-20261102, Community edition.)

The download is free, with no sign-in and no time limit. One zip holds a standard Odoo backup and a small Docker file that uses the
official Odoo and PostgreSQL images. New days every night are optional, in the same download: see [New days every night](#new-days-every-night-optional).

## Four ways to use Northstar

1. **Download it** (Available now): Download northstar-odoo20.zip from the latest release, unzip it into an empty folder, run `docker compose up` and open Odoo on your own computer. Free, no sign-in.
2. **Ask it with AI** (Available now): Sign in free at [speaktoyourdatabase.com](https://speaktoyourdatabase.com/northstar?utm_source=github&utm_medium=readme), get 20 free prompts and ask Northstar in ChatGPT, Claude or the Speak To Your Database chat. It is the sample every new account has.
3. **Load it into your own Odoo** (Coming soon): Load Northstar into your own empty Odoo 20 with an administrator API key, then a new day every night.
4. **Keep your download alive** (Coming soon): Your downloaded copy keeps living on your computer, a new day every night.

**Running Northstar on a server? Our free guides:**

- [Secure Odoo on a VPS](https://www.universal-db-ai.com/guides/secure-odoo-vps?utm_source=github&utm_medium=readme)
- [Odoo on a subdomain with HTTPS](https://www.universal-db-ai.com/guides/odoo-subdomain-https?utm_source=github&utm_medium=readme)
- [Complete Odoo backups](https://www.universal-db-ai.com/guides/odoo-backup-best-practices?utm_source=github&utm_medium=readme)
- [A safe Odoo sandbox](https://www.universal-db-ai.com/guides/odoo-sandbox-environment?utm_source=github&utm_medium=readme)

**Planning Odoo for your own company?** We install it, migrate your data and build what you need: [https://speaktoyourdatabase.com/catalogue?utm_source=github&utm_medium=readme](https://speaktoyourdatabase.com/catalogue?utm_source=github&utm_medium=readme)

## What Northstar is

- **One company's year, run in Odoo.** Quotes become sales orders, deliveries, invoices and payments. Stock is bought from vendors when it
  runs low and received late when a vendor is slow. A trade counter sells over the counter with Point of Sale. A small assembly workshop
  builds products to order and to stock. 25 people work in 8 departments, take time off and clock in and out. Leads come in every month
  and are won or lost with a reason.
- **Books that add up.** Inventory valuation equals the stock on hand to the cent, sales tax is collected and paid to the state every
  month, payroll and running costs are booked, the balance sheet balances.
- **Stories worth finding.** Customers who pay late, a key account that fades out, a popular product that keeps running out, dead stock,
  a vendor who delivers late, quotes lost to price or a competitor, a new eco-friendly line, a strong fourth quarter.

## What Northstar is not

- **Not random records.** Every figure follows from a plan of one company's year, so totals, trends and the links between apps make sense.
- **Not a real company.** Names, addresses, emails (on `.example` domains), phone numbers (555-01xx) and tax IDs are invented. The one
  exception is us: Speak To Your Database, which made Northstar, appears in it as Northstar's software and Odoo supplier, with our contact
  address and our founder, who agreed to it. No other real person, business or transaction is shown. Every PDF footer and the About note
  in the database say so.
- **Not Odoo's own demo data, and not Enterprise.** It is built on Odoo 20 Community only.

## What is inside

Apps: Sales, CRM, Purchase, Inventory, Invoicing, Point of Sale, Manufacturing, Employees, Time Off, Attendances, Project, Timesheets and To-Do, connected to each other.

| App | Records | Count |
|---|---|---|
| Sales | Quotations and sales orders | 2,194 |
|  | Confirmed sales orders | 1,321 |
|  | Sales order lines | 6,398 |
| CRM | Leads and opportunities (won, lost and open) | 613 |
|  | Won opportunities | 282 |
|  | Lost (archived with a reason) | 302 |
| Purchase | Purchase orders | 478 |
| Inventory | Products (sold, bought, made) | 159 |
|  | Transfers done (receipts, deliveries) | 2,223 |
|  | Stock moves done | 10,742 |
| Invoicing | Customer invoices | 1,835 |
|  | Customer credit notes | 70 |
|  | Vendor bills | 645 |
|  | Payments | 2,346 |
|  | Journal entries posted (all kinds) | 5,410 |
| Point of Sale | Counter sessions | 251 |
|  | Counter tickets (refunds included) | 3,529 |
| Manufacturing | Manufacturing orders | 180 |
|  | Work orders | 447 |
|  | Bills of materials | 9 |
| Employees | Employees (active) | 25 |
|  | Departments | 8 |
| Time Off | Time off requests | 115 |
|  | Allocations | 88 |
| Attendances | Attendance records | 1,379 |
| Project | Projects | 44 |
|  | Tasks | 452 |
| Timesheets | Timesheet lines | 1,418 |
| Contacts | Customer companies | 150 |
|  | Vendor companies | 37 |

The full list, with the build date and the checksum of the file, is in `northstar-manifest.json` on the release page.

## Run it with Docker (Windows, macOS, Linux)

1. Install Docker Desktop (Windows, macOS) or Docker Engine with the Compose plugin (Linux). Docker Compose 2.20 or later is needed; every
   current Docker Desktop has it.
2. [Download Northstar](https://github.com/speaktoyourdatabase/northstar-odoo-demo/releases/latest/download/northstar-odoo20.zip) (`northstar-odoo20.zip`, about 8.7 MB) and unzip it into an empty folder. It holds the Docker
   file, the database, this README, the checksums and the files of the optional new days every night, and nothing else is needed.
3. Open a terminal in that folder and run:

   ```
   docker compose up
   ```

4. The first start takes a few minutes, and this is normal: Docker downloads the two official images once, then Northstar prints
   `Restoring Northstar` and a `Still restoring` line every 10 seconds (usually 60 to 120 seconds in all). You do not need to do anything.
5. When you see `Northstar is ready`, open the address. The window stays open while Northstar runs.
   Log in with one of the logins below.

Good to know:

- Later starts keep your data and open in seconds. Stop with `Ctrl+C` (or `docker compose down`), start again with `docker compose up`.
  Left running when the computer restarts, Northstar starts again with Docker; once stopped, it stays stopped.
- If the restore fails, Northstar prints one line that says what failed, what to do and the command that shows the details.
- Port 8069 already in use? Run `NORTHSTAR_PORT=8079 docker compose up` (PowerShell: `$env:NORTHSTAR_PORT=8079; docker compose up`).
- Start over with the original data: `docker compose down -v`, then `docker compose up`. This deletes every change you made.
- Odoo listens on your own computer only (127.0.0.1), not on your network. Nothing connects to our service unless you switch on the new days below.

## New days every night (optional)

**New days every night (optional): `docker compose --profile live up -d`, then open <http://localhost:8070> and click Pair.**

The data stops on 10 November 2026. Northstar Live keeps your copy alive: every night we add the day that just ended (quotes, orders,
deliveries, invoices, payments, purchases, the trade counter, the workshop, projects, time off, leads), and the days since 10 November 2026
are caught up first. It is off until you switch it on, and it uses this same install: same data, nothing to download again but our
small relay. It needs a free account at <https://speaktoyourdatabase.com/northstar?utm_source=github&utm_medium=readme>.

**Opening soon.** Our Live service is not open yet. Until it is, the relay's page says it is not connected and nothing else changes.

1. In the Northstar folder, run:

   ```
   docker compose --profile live up -d
   ```

2. Open <http://localhost:8070>. It shows your pairing code in large type, the time it is valid (15 minutes) and a big button,
   **Pair with Speak To Your Database**. Click it: our site opens in a new tab with the code already filled in. Sign in to your free account
   and confirm. Do it on the same network as this computer (the same internet connection): a pairing from another network is refused.
3. The page switches to **Live** by itself.

No browser on that computer? `docker compose exec northstar-live northstar-live code` prints the code and the full link: open the link on
another device of the same network. You can also type the code yourself on our site (the **Copy code** button helps).

How it works, and what it can and cannot do:

- Without `--profile live`, nothing in this package connects to our service: the relay does not start and its image is not even downloaded.
- With it, a small relay (`northstar-live`) opens one **outgoing** encrypted connection to our service. Nothing listens on your network:
  Odoo and the relay's page are on 127.0.0.1 only.
- Your Odoo API key is made on your computer when Live starts and **never leaves it**. The relay adds it to each call itself.
- The relay passes to your Odoo the calls of Northstar's daily life and only those (about 60 Odoo models, with limits on size, time and
  pace). It cannot reach any other address, use the database manager, read or change users, passwords, rights or API keys, install apps,
  run code in Odoo, send email or delete records.
- Leave it running. A night when the computer is off is caught up when it is back, up to 45 days.
- With Live on, add `--profile live` to stop and start over: `docker compose --profile live stop` stops everything,
  `docker compose --profile live up -d` starts it again, and `docker compose --profile live down -v` starts over with the original data
  (it also forgets the pairing). The relay alone: `docker compose stop northstar-live` (Odoo keeps working; the missed days come later).
- Disconnect this computer from its account: the button on <http://localhost:8070> (tick the box first), or
  `docker compose exec northstar-live northstar-live unpair`. Your Odoo and your changes stay. To pair it with another account, disconnect it first.
- Memory: about 450 MB after a night (the relay about 26 MB, capped at 128 MB). In Docker Desktop, leave at least 4 GB to Docker.
- The relay's page shows when it last heard from our service and when it last changed your Odoo; `docker compose logs northstar-live` shows
  what it did, never your key, the pairing code or your data.

## Restore it without Docker (Odoo database manager)

The package holds the database as `northstar-odoo20-2026-11-10.zip`, a standard Odoo backup (`dump.sql`, `filestore`, `manifest.json`). It restores on any
self-hosted Odoo 20 Community:

1. Open `/web/database/manager` on your Odoo 20 (for example <http://localhost:8069/web/database/manager>).
2. Click **Restore Database**, enter your master password, choose `northstar-odoo20-2026-11-10.zip` (unzip the package first), name the database `northstar`.
3. Keep **This database is a copy** selected (it gives the restored database its own identity), then click **Continue**.
4. Open the new database and log in with one of the logins below.

If the upload stops, raise the upload size limit of your web server or proxy (for example `client_max_body_size` in nginx).

## Logins

| Person | Login | Password |
|---|---|---|
| Administrator | `admin` | `admin` |
| Rachel Donovan | `rachel.donovan@northstar-supply.example` | `northstar` |
| Marcus Hale | `marcus.hale@northstar-supply.example` | `northstar` |
| Priya Raman | `priya.raman@northstar-supply.example` | `northstar` |
| Tomas Kowalski | `tomas.kowalski@northstar-supply.example` | `northstar` |

**These passwords are public.** They are fine on your own computer. Before you put this database on a server that other people can reach,
change every user's password, the database manager's master password (`admin_passwd` in your Odoo configuration) and the PostgreSQL
password in `docker-compose.yml`.

Northstar sends no email: the database has no mail server, and every address is on a `.example` domain that cannot receive mail.

## Fresh data

**Data until 10 November 2026, refreshed every week.** We publish a new release every week; its 12 months of history end the day before it
was built. Your copy does not change by itself (unless you switch on the new days every night above): to move to a newer release, download the
package again, run `docker compose down -v` in the old folder (`docker compose --profile live down -v` if Live is on), unzip the new package into a
new empty folder and run `docker compose up` there.

## Licence and credit

Northstar is released under **CC0 1.0 Universal** (public domain dedication, see [LICENSE](LICENSE)): use, copy, change and share it for any
purpose, private or commercial, with no permission needed. Credit is asked, not required. If you show it, publish screenshots or build
on it, we would be glad of a short credit:

```
Demo data: Northstar by Speak To Your Database, speaktoyourdatabase.com/northstar
```

More about Northstar: <https://speaktoyourdatabase.com/northstar?utm_source=github&utm_medium=readme>

You can also ask Northstar questions in plain words in ChatGPT or Claude through Speak To Your Database.

## FAQ

**Is any of it real?** No. The company, its customers, vendors, products, people and every document are fictional and generated.

**Is this the sample company inside Speak To Your Database?** Yes, it is the same company: you can ask it questions in plain words in
ChatGPT or Claude through Speak To Your Database. That hosted copy is refreshed on its own schedule, so its latest days can differ from
this release.

**How often is it refreshed?** It is refreshed every week. The data-until date is at the top of this page and in every release.

**Which Odoo version do I need?** Odoo 20 Community, build 20.0-20261102 or later. The Docker file pins the images this release was
tested with (`odoo:20.0-20261102`, `postgres:16`), and the optional relay by its digest.

**Does the download connect to your service?** No. Only if you switch on the new days every night with `docker compose --profile live up -d`:
then the relay connects out to our service, and nothing else does.

**Can I trust the download?** The package holds `SHA256SUMS` with the SHA-256 of every file in it, the release page shows the SHA-256 of
the package, and `northstar-manifest.json` has the one of the database file. Docker's restore step checks the database file against
`SHA256SUMS` before it starts.

**Can I use it at work, in training or in a product demo?** Yes. It is CC0 1.0: see [LICENSE](LICENSE) and [TERMS.md](TERMS.md).

**Questions?** Write to contact@speaktoyourdatabase.com.

Speak To Your Database
