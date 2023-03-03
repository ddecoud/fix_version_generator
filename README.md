# Fix Version Generator

Fix version generator using the Jira API. The logic currently implemented is as follows:

Given a PROJ in JIRA, a date range and the first starting fix version. This tool will generate:

- **Major releases**, each week's major.
- **Minor releases**, each week's minor.

## Usage

```sh
usage: fix_version_gen.py [-h] [-f {WEEKLY,EVERY_TWO_WEEKS,MONTHLY}] [-ma {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}]
                          [-mi {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}]
                          jira_project start_date end_date version

positional arguments:
  jira_project          Specify Jira project name
  start_date            Specify fix version start date. Format YYYYMMDD
  end_date              Specify fix version end date. Format YYYYMMDD
  version               Specify fix version number. Following this format: 'Feature.Mayor.Minor'. Example: 1.1.0

optional arguments:
  -h, --help            show this help message and exit
  -f {WEEKLY,EVERY_TWO_WEEKS,MONTHLY}, --freq {WEEKLY,EVERY_TWO_WEEKS,MONTHLY}
                        Specify the frequency of release. (default: WEEKLY)
  -ma {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}, --major {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}
                        Specify the weekday of major release. (default: MONDAY)
  -mi {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}, --minor {MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY}
                        Specify the weekday of minor release. (default: THURSDAY)
```

## Example

```bash
./fix_version_gen.py DEV 2022-08-01 2022-09-01 1.12.0 -f WEEKLY
```
