# CHANGELOG

# v0.12.0

- Support additional credit card expected header format (thanks [Dr-Nuke])

# v0.11.0

- Use "Wertstellung" instead of "Belegdatum" for transaction dates in
  `CreditImporter` (thanks [@nils-werner])

# v0.10.0

- Add `meta_code` parameter to `ECImporter` (thanks [@bratekarate])

# v0.9.0

- Support credit data exports containing "Zeitraum" instead of "Von"/"Bis" dates
- Update `CreditImporter.file_date` return value (end date if the export
  contains start/end dates, otherwise the date of the export itself)

# v0.8.3

- Enable support for Python 3.9
- Drop support for Python 3.5

## v0.8.2

- Return date of last transaction from `file_date` for `CreditImporter`

## v0.8.1

- Add account number to narration if there's no transfer text (thanks [@tbm])
- Add optional parameter `existing_entries` to `extract()` (thanks [@tbm])

## v0.8.0

- Enable support for Python 3.8

## v0.7.1

- Fix parsing "Saldo" amounts in `CreditImporter` (#84)

## v0.7.0

- Replace `locale` based parsing of numbers with a simple helper function
- specifically for handling German formatting of numbers

## v0.6.4

- Add a `timedelta` of 1 day when setting the date on the `balance` directive
  outputs to make things consistent between what Beancount expects (balance
  amount valid from the beginning of the day) and what DKB exports contain
  (balance amount valid at the end of the day)

## v0.6.3

- Fix date value on `balance` that `ECImporter` outputs

## v0.6.2

- Support Python 3.7
- Implement `file_date` for `CreditImporter`
- Set `payee` in `CreditImporter` postings to `None` because of missing data
- Include additional assertions for matching dates in metadata entries in
  `ECImporter`

## v0.6.1

- Handle empty amount strings for `Tagessaldo` entries in `ECImporter` (thanks
  [@dmerkert])

## v0.6.0

- Emit closing `balance` directive based on the "Saldo" metadata entry
  (thanks [@dmerkert])

## v0.5.1

- Emit correct line numbers when constructing new metadata in `ECImporter`

## v0.5.0

- Differentiate between "Auftraggeber/Begünstigter" and "Verwendungszweck"
  (thanks [@niels])
- Implement `file_date` returning the closing date of the statement (thanks
  [@niels])
- Emit closing `balance` directive based on the "Kontostand vom" metadata
  entry (thanks [@niels])

## v0.4.0

- Ignore user-assigned account names in `ECImporter` (thanks [@niels])

## v0.3.1

- Support updated header format in `CreditImporter`

## v0.3.0

- Emit `balance` directive for `Tagessaldo` entries in `ECImporter`
- Remove unused `ignore_tagessaldo` parameter from `CreditImporter`

## v0.2.1

- Fix metadata keys in CreditImporter

## v0.2.0

- Added CreditImporter to import CSV exports of Credit Cards

## v0.1.0

- Added ECImporter to import CSV exports of EC accounts


[@bratekarate]: https://githun.com/bratekarate
[@dmerkert]: https://github.com/dmerkert
[@Dr-Nuke]: https://github.com/Dr-Nuke
[@niels]: https://github.com/niels
[@nils-werner]: https://github.com/nils-werner
[@tbm]: https://github.com/tbm
