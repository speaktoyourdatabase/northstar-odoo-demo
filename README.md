# Northstar: a fictional company for Odoo 20 Community

Northstar Office & Industrial Supply Inc. is a fictional US company in Columbus, Ohio: a B2B distributor of office, facility and light
industrial supplies with about 25 employees. It comes as a ready-to-run Odoo 20 Community database with 12 months of history, every app
connected to the others, and books that are right to the cent.

**Data until 7 November 2026, refreshed every month.** (History from 7 November 2025. Odoo 20.0-20261102, Community edition.)

Free, no sign-in, no time limit. Data only: you get a standard Odoo backup and a small Docker file that uses the official Odoo and
PostgreSQL images.

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
- **Not a real company.** Names, addresses, emails (on `.example` domains), phone numbers (555-01xx) and tax IDs are invented. No real
  person, business or transaction is shown. Every PDF footer and the About note in the database say so.
- **Not Odoo's own demo data, and not Enterprise.** It is built on Odoo 20 Community only.

## What is inside

Apps: Sales, CRM, Purchase, Inventory, Invoicing, Point of Sale, Manufacturing, Employees, Time Off, Attendances, Project, Timesheets and To-Do, connected to each other.

| App | Records | Count |
|---|---|---|
| Sales | Quotations and sales orders | 2,194 |
|  | Confirmed sales orders | 1,313 |
|  | Sales order lines | 6,370 |
| CRM | Leads and opportunities (won, lost and open) | 603 |
|  | Won opportunities | 273 |
|  | Lost (archived with a reason) | 298 |
| Purchase | Purchase orders | 472 |
| Inventory | Products (sold, bought, made) | 147 |
|  | Transfers done (receipts, deliveries) | 2,205 |
|  | Stock moves done | 10,690 |
| Invoicing | Customer invoices | 1,830 |
|  | Customer credit notes | 70 |
|  | Vendor bills | 624 |
|  | Payments | 2,316 |
|  | Journal entries posted (all kinds) | 5,355 |
| Point of Sale | Counter sessions | 250 |
|  | Counter tickets (refunds included) | 3,514 |
| Manufacturing | Manufacturing orders | 175 |
|  | Work orders | 441 |
|  | Bills of materials | 9 |
| Employees | Employees (active) | 25 |
|  | Departments | 8 |
| Time Off | Time off requests | 113 |
|  | Allocations | 88 |
| Attendances | Attendance records | 1,399 |
| Project | Projects | 53 |
|  | Tasks | 479 |
| Timesheets | Timesheet lines | 1,412 |
| Contacts | Customer companies | 150 |
|  | Vendor companies | 37 |

The full list, with the build date and the checksum of the file, is in `northstar-manifest.json` on the release page.

## Run it with Docker (Windows, macOS, Linux)

1. Install Docker Desktop (Windows, macOS) or Docker Engine with the Compose plugin (Linux).
2. From the latest release, download two files into one empty folder: `northstar-odoo20-2026-11-07.zip` (8.7 MB) and `docker-compose.yml`.
3. Open a terminal in that folder and run:

   ```
   docker compose up
   ```

4. The first start downloads the two official images once, then restores the database (one or two minutes on a laptop). When you see
   `Northstar restored`, open <http://localhost:8069> and log in
   with one of the logins below.

Good to know:

- Later starts keep your data and open in seconds. Stop with `Ctrl+C` (or `docker compose down`), start again with `docker compose up`.
- Port 8069 already in use? Run `NORTHSTAR_PORT=8070 docker compose up` (PowerShell: `$env:NORTHSTAR_PORT=8070; docker compose up`).
- Start over with the original data: `docker compose down -v`, then `docker compose up`. This deletes every change you made.
- Odoo listens on your own computer only (127.0.0.1), not on your network.

## Restore it without Docker (Odoo database manager)

The same zip is a standard Odoo backup (`dump.sql`, `filestore`, `manifest.json`). It restores on any self-hosted Odoo 20 Community:

1. Open `/web/database/manager` on your Odoo 20 (for example <http://localhost:8069/web/database/manager>).
2. Click **Restore Database**, enter your master password, choose `northstar-odoo20-2026-11-07.zip`, name the database `northstar`.
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

## Fresh every month

**Data until 7 November 2026, refreshed every month.** Each month we publish a new release whose 12 months of history end the day before it
was built. Your copy does not change by itself: to move to a new month, download the new zip, run `docker compose down -v`, replace the old
zip with the new one and run `docker compose up`.

## Licence and credit

Northstar is released under **CC0 1.0 Universal** (public domain dedication, see [LICENSE](LICENSE)): use, copy, change and share it for any
purpose, private or commercial, with no permission needed. Credit is asked, not required. If you show it, publish screenshots or build
on it, we would be glad of a short credit:

```
Demo data: Northstar by Speak To Your Database, speaktoyourdatabase.com/northstar
```

More about Northstar: <https://speaktoyourdatabase.com/northstar>

You can also ask Northstar questions in plain words in ChatGPT or Claude through Speak To Your Database.

## FAQ

**Is any of it real?** No. The company, its customers, vendors, products, people and every document are fictional and generated.

**Is this the sample company inside Speak To Your Database?** Yes, it is the same company: you can ask it questions in plain words in ChatGPT or Claude through Speak To Your Database. That hosted copy is refreshed on its own schedule, so its latest days can differ from this release.

**Which Odoo version do I need?** Odoo 20 Community, build 20.0-20261102 or later. The Docker file pins the images this release was
tested with (`odoo:20.0-20261102`, `postgres:16`).

**Can I trust the download?** Each release lists the SHA-256 of the zip in `SHA256SUMS` and in `northstar-manifest.json`.

**Can I use it at work, in training or in a product demo?** Yes. It is CC0 1.0: see [LICENSE](LICENSE) and [TERMS.md](TERMS.md).

**Questions?** Write to contact@speaktoyourdatabase.com.

Speak To Your Database
