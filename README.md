# SolidInvoice (LazyCat LPK)

Invoicing and quoting for freelancers and small businesses.

- Upstream: https://github.com/SolidInvoice/SolidInvoice (branch `3.2.x`)
- Image: `solidinvoice/solidinvoice:3.1.2` (mirror mode, digest-matched)
- License: MIT (full text in `content/licenses/LICENSE`)
- Containers: single (SQLite)

## Notes

- Ships a full install bundle: `src/InstallBundle/` with an `Install` action, an
  `InstallCommand`, and an `IsInstalledCommand` — so the first admin is created through
  the web installer, no seeded credential.
- SQLite is supported: `src/InstallBundle/Config/DatabaseConfig.php` lists `sqlite`/`sqlite3`
  in `$driverSchemeAliases`, and `DATABASE_URL=sqlite:////data/solidinvoice.db` keeps this
  single-container.
- `APP_SECRET` comes from a platform stable secret. Mailer set to `null://null` since no
  mail service is configured.
- Data on `/lzcapp/var/data`.
- Not yet verified on a real device.
