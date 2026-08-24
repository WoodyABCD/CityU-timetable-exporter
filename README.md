# CityU Timetable Exporter — Convert AIMS Schedule to ICS Calendar

**City University of Hong Kong (CityU / 香港城市大學)** students: export your **AIMS student detail schedule** to an **ICS calendar file** and import it into **Google Calendar**, **Apple Calendar**, **Outlook**, or any calendar app.

No more typing lectures by hand. Copy your weekly timetable from AIMS, paste it here, download `.ics`.

**Use the web app (no install):** [https://woodyabcd.github.io/CityU-timetable-to-ics-exporter/](https://woodyabcd.github.io/CityU-timetable-to-ics-exporter/)

---

## What this tool does

CityU AIMS shows your **class timetable** (CRN, course code, lecture / tutorial / lab, room, weekday, date range). This exporter parses that text and generates a standard **iCalendar (.ics)** file with recurring weekly events.

Works with:

- CityU **AIMS** → Course Registration → Weekly Schedule → **Student Detail Schedule**
- **Google Calendar** import
- **Apple Calendar** (iPhone, iPad, Mac) — choose “New Calendar” so the calendar is named after the file
- **Microsoft Outlook** and other apps that support ICS / iCal

Keywords people search: *CityU timetable*, *CityU calendar*, *AIMS ICS*, *CityU Google Calendar*, *城大時間表匯出*, *城大行事曆*, *CityU HK class schedule*.

---

## Web version (recommended)

Open: **[CityU Timetable to ICS Exporter](https://woodyabcd.github.io/CityU-timetable-to-ics-exporter/)**

1. Log in to **AIMS**.
2. Go to **Course Registration** → **Weekly Schedule** → **Student Detail Schedule** (list view where **CRN** is visible).
3. Select all (**Ctrl+A** / **Cmd+A**) and copy.
4. Paste into the web page (or upload a `.txt` file).
5. Click **Convert & Download ICS**.
6. Open the `.ics` file in Google Calendar, Apple Calendar, or Outlook.

Runs in the browser. Course data stays on your device.

---

## Get source data from AIMS

1. Log in to **AIMS** (CityU student portal).
2. Navigate: `Course Registration` → `Weekly Schedule` → `Student Detail Schedule`.
3. Copy the full page (**Ctrl+A**, **Ctrl+C**) into the web app or a file such as `schedule.txt`.

Expected content includes course title, CRN, class times (e.g. `10:00 AM - 11:50 AM`), weekday letters (`M T W R F S U`), venue (Yeung / AC1, Li / AC2, Bank of China / BOC, etc.), and date range.

---

## Command-line usage (Java)

Requires **Java**. From the project root:

```bash
java Main.java <filename>
```

Example:

```bash
java Main.java schedule.txt
```

This writes `schedule.ics`. Double-click the file to import.

**Apple Calendar:** when importing, choose **New Calendar** so the calendar name matches the output filename.

### Options

| Option | Description |
| --- | --- |
| `-h`, `--help` | Show help |
| `-o`, `--output <file>` | Output ICS name (without `.ics`) |
| `-s`, `--setfile <file>` | Input text file |
| `-d`, `--toDifferentFile` | One ICS file per course |

Examples:

```bash
java Main.java -s schedule.txt -o CityU-Semester-A
java Main.java -s schedule.txt -d
```

---

## Features

- Parses CityU **AIMS Student Detail Schedule** text
- Recurring weekly events until the semester end date
- Maps campus buildings (Yeung → AC1, Li → AC2, Bank → BOC, and others)
- Event titles include venue, course id, and class type
- Web UI and Java CLI
- Import into Google Calendar, Apple Calendar, Outlook

---

## Project layout

| Path | Role |
| --- | --- |
| [docs/index.html](docs/index.html) | Web UI |
| [docs/script.js](docs/script.js) | Browser parser and ICS download |
| [Main.java](Main.java) | CLI entry |
| [DataReader.java](DataReader.java) | Parse AIMS text |
| [ICSExporter.java](ICSExporter.java) | Write `.ics` |

GitHub Pages serves `docs/`.

---

## Privacy

The web version converts the timetable in your browser. Nothing is uploaded to a server for conversion.

---

## Related searches

CityU HK timetable exporter, City University of Hong Kong AIMS calendar, export CityU class schedule to Google Calendar, CityU ics, 香港城市大學 AIMS 時間表 ICS, 城大課程表匯入日曆, CityU student detail schedule to iCal.

---

## License and contribution

Built for CityU students. Issues and pull requests are welcome.

**Live tool:** [woodyabcd.github.io/CityU-timetable-to-ics-exporter](https://woodyabcd.github.io/CityU-timetable-to-ics-exporter/)
