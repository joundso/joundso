# Review: Final ITB Homepage (Stand 18.08.2026)

Geprüft: [https://final-itb.netlify.app](https://final-itb.netlify.app) (HTTP `final-itb.de` leitet dorthin um).
Die Quelltexte der Quarto-Seite liegen **nicht** in diesem GitHub-Profil-Repo. Die folgenden Punkte sind als Checkliste für das eigentliche Website-Repo gedacht.

Kontaktdaten, USt-IdNr. und Adresse im Impressum wirken stimmig zur E-Mail `info@final-itb.de`. Der inhaltliche Kern („Zweitmeinung / Gutachten / Medizinische Informatik“) ist gut. Drumherum wirkt die Seite wie ein früher Quarto-Entwurf: generische IT-Leistungsliste, GitHub-Profil-Logos, Platzhalter-Vorträge, rechtlich veraltete Bausteine.

---

## Zuerst erledigen (Aktualität und Risiko)

### 1. Impressum: TMG → DDG

Das Impressum zitiert noch **§ 5 TMG** und **§§ 7–10 TMG**. Das Telemediengesetz ist seit 14.05.2024 durch das **Digitale-Dienste-Gesetz** abgelöst. Üblich ist jetzt **§ 5 DDG** bzw. der Gesetzesverweis ganz weglassen. Die Haftungsabsätze sollten ebenfalls auf DDG/DSA geprüft werden, nicht auf aufgehobenes TMG.

Zusätzlich hängt im Impressum ein verkürzter Datenschutz-Absatz, der der eigenen Datenschutzerklärung widerspricht (Analytics, Cookies, Drittländer). Den Abschnitt im Impressum streichen; nur auf `/qmd/datenschutz` verlinken.

### 2. Cookie-Banner und Google Analytics

Aktuell:

- Google Analytics `G-0J0X8CTBQR`
- Cookie-Consent **`implied`** (Nutzung gilt als zugestimmt)
- Beim Laden werden Tracking- und Targeting-Level gesetzt
- Privacy-URL zeigt auf `/qmd/datenschutz.qmd` → **404**
- Banner-Sprache: Englisch

Für Tracking-Cookies gilt in DE Einwilligung **vor** dem Setzen (TDDDG). Implied Consent reicht dafür nicht.

**Einfachste Lösung für ein Nebengewerbe:** Analytics weglassen. Dann braucht es keinen Tracking-Banner. Die Datenschutzerklärung (Stand 26.10.2023) entsprechend kürzen und neu datieren.

Falls Analytics bleiben soll: echtes Opt-in, deutsche Texte, korrekte Privacy-URL `/qmd/datenschutz`.

### 3. AGB passen nicht zum Geschäft

Die AGB sind **Verkaufsbedingungen für Ware** (ab Werk, Verpackung, Kaufsache, Lager, Eigentumsvorbehalt, Weiterveräußerung, § 377 HGB). Final ITB verkauft Beratung, Gutachten, Einrichtung und Softwarearbeit – keine Stückgüter ab Lager.

Das ist rechtlich und gegenüber Kunden unpassend. Entweder echte **Dienstleistungs-AGB** (Leistungsbeschreibung, Mitwirkung, Abnahme, Vergütung/Stundensatz vs. Festpreis, Haftung, Vertraulichkeit, DSGVO-Auftragsverarbeitung) oder den Menüpunkt vorerst entfernen, bis ein Text von einem Anwalt sitzt.

### 4. HTTPS auf `final-itb.de`

`http://final-itb.de` funktioniert und leitet nach Netlify um. `https://final-itb.de` schlägt fehl. Die E-Mail-Domain ist `final-itb.de`, die sichtbare Website aber `*.netlify.app`.

In Netlify die Custom Domain inkl. Let’s-Encrypt-Zertifikat aktivieren und überall `https://final-itb.de` verwenden.

---

## Inhalt: was nicht mehr bzw. nie aktuell war

### Startseite

- Die drei Fragen unter „Sie suchen …“ sind der stärkste Teil. Die Dienstleistungsliste darunter klingt nach Stellenbeschreibung einer internen IT-Abteilung („Kostenmanagement in der IT-Abteilung“, Hardwarebeschaffung, Anwender-Support). Für eine Beratungsseite besser 3–4 Angebote mit Nutzen.
- Logo-Leiste: 1:1 vom GitHub-Profil, viele **tote Hotlinks** (siehe unten). Auf einer Firmenhomepage wirken 20 Tool-Logos wie ein Entwickler-README, nicht wie ein Angebot.
- Kommentierter Quelltext deutet an, dass Vorträge, Cloud, Kubernetes, FHIR-Analysen geplant waren – live fehlt genau das, was dich von einem allgemeinen IT-Dienstleister unterscheidet.
- UI-Sprache Englisch (`lang="en"`, Home, Search, On this page, Back to top) bei durchgehend deutschem Inhalt.

### Kontakt (`/qmd/contact`)

Bitte gegen den aktuellen Lebenslauf gegenchecken:

| Angabe auf der Seite | Öffentlich abweichend |
| --- | --- |
| Uniklinikum Erlangen, IFM, Teamleitung, 2020–heute | LinkedIn: Teamleitung Transferstelle DIZ; Postdoc am Lehrstuhl MI seit Aug. 2023 |
| Ph.D. Sep 2019 – Jul 2023 | LinkedIn: 2020–2023 |
| Portrait-Dateiname `MA-Portrait_lowQuality_quadratic.jpg` | wirkt unfreiwillig; besseres Foto, neutrale Dateinamen |

Die Ausbildung (B.Sc./M.Sc. Medizintechnik, Dr. Medizininformatik) ist plausibel und sollte prominent bleiben. Fürs Nebengewerbe reicht eine kurze Qualifikationszeile, kein voller akademischer CV.

### Vorträge (`/qmd/talks`)

Die sechs Titel klingen nach generischen Seminar-Prompts (Cybersicherheit, Big Data, agiles PM, Ethik, digitale Transformation, Remote-Teams). Keine Daten, Orte, Folien, Zielgruppen. Deine tatsächliche Expertise (FHIR, Datenqualität, REDCap, DIZ, Forschungsdaten) kommt nicht vor.

Entweder echte Vorträge eintragen oder die Seite aus der Navigation nehmen. Leere Versprechen schaden mehr als eine fehlende Seite.

### LinkedIn-Firma vs. Website

Die LinkedIn-Unternehmensseite erwähnt u. a. **KHZG**. Neue KHZG-Anträge laufen nicht mehr; bewilligte Projekte enden 2026. Für Klinik-IT ist 2026 eher **KHVVG / Transformationsfonds (KHAG)** das aktuelle Förderumfeld – und nur, wenn du das wirklich anbietest. Auf der Website fehlt dieser Kontext sowieso; nicht nachziehen, nur um ein Buzzword zu haben.

---

## Kaputte Logos auf der Live-Seite

Dieselben Wikimedia-Thumbnails und alte Asset-URLs, die im GitHub-Profil bereits ersetzt wurden, sind auf Final ITB noch live. Derzeit u. a. 400/404:

- Java, RStudio, Raspberry Pi, Ubuntu, VMware, Jira, Confluence (Wikimedia-Thumbnails)
- VS Code (`code-stable.png`), Jupyter (altes Logo-SVG), Kubernetes (`kubernetes-horizontal-color.png`), REDCap (Charité-URL)

Zusätzlich:

- Kubernetes-Bild hat `alt="vmware"`
- Bash-Link zeigt auf `bashtop.html` statt auf GNU Bash
- Hotlinking zu Wikimedia, GitHub, Charité, kubernetes.io ist ohnehin instabil

**Empfehlung:** Logos lokal unter `img/logos/` ablegen oder die Logo-Wand auf der Firmenhomepage weglassen. Wenn sie bleiben: die bereits korrigierten SVG-URLs aus `README.md` dieses Repos übernehmen.

---

## Was die Seite besser machen kann (Wirkung)

Die Seite erklärt *was du tun kannst*, aber nicht *für wen* und *warum du*. Als Nebengewerbe gewinnst du Aufträge über Vertrauen und Spezialisierung, nicht über eine volle Leistungskarte.

1. **Eine klare Positionierung oben**, z. B. „Unabhängige IT-Beratung und medizinische Informatik in Erlangen – Gutachten, Zweitmeinung, FHIR/Datenqualität, praxisnahe Infrastruktur.“
2. **Zielgruppe benennen:** Arztpraxis / MVZ, Klinik-IT bzw. Forschung, kleines Unternehmen in der Region. Nicht alle drei gleich laut – der erste Satz entscheidet.
3. **Drei Angebote statt neun Bulletpoints**, jeweils mit einem Satz Ergebnis:
   - Unabhängiges Gutachten / Zweitmeinung
   - Medizinische Informatik (FHIR, Datenqualität, R, REDCap, Datenschutz im Gesundheitswesen)
   - Infrastruktur für kleine Teams (Netzwerk, Backup, Linux/Proxmox, nachvollziehbare Doku)
4. **Einen Call-to-Action:** „Kurz schildern, worum es geht“ → Mail `info@final-itb.de`. Der Kontakt-Block auf der Startseite ist gut, aber ohne Button und ohne Erwartung (Antwortzeit, Erstgespräch).
5. **Person zeigen:** Name, Dr. med. Inf., seit 2012 nebenberuflich, Foto in anständiger Qualität. Das unterscheidet dich von Agentur-Texten.
6. **Keine Tool-Logos als Kompetenzbeweis.** Lieber 4–6 Themen als Text (FHIR, R, Datenschutz, Proxmox, Docker, REDCap).
7. **SEO-Basics:** `lang="de"`, Title nicht nur „Final ITB“, Meta-Description, Open Graph, Canonical auf `https://final-itb.de`. Quarto-Suche in der Navbar ist für fünf Seiten überflüssig.
8. **Technik-Logos und GitHub-Stats gehören aufs Profil**, nicht auf die Gewerbliches-Angebot-Seite.

---

## Textvorschlag Startseite (zum Übernehmen ins Quarto-`index`)

Kurz, deutsch, ohne Platzhalter. An Zielgruppe und Ton anpassen, bevor er live geht.

```markdown
# IT-Beratung und medizinische Informatik

Unabhängige Zweitmeinung, Gutachten und Umsetzung – für Praxen, Forschung und kleine Organisationen in der Region Erlangen.

**Dr. Jonathan Mang** · Final ITB · nebenberuflich seit 2012

[Kurzbeschreibung schicken](mailto:info@final-itb.de)

## Wobei ich helfe

### Gutachten und Zweitmeinung
Bewertung von IT-Infrastruktur, geplanten Projekten oder Angeboten Dritter – nachvollziehbar, herstellerunabhängig.

### Medizinische Informatik
FHIR, Datenqualität, R-Analysen, REDCap, Datenschutz im Gesundheitswesen. Übersetzung zwischen Klinik, Forschung und IT.

### Infrastruktur, die im Alltag trägt
Planung, Einrichtung und Wartung von Netzwerken, Servern und Backup – inkl. Dokumentation, damit ihr nicht von einer Person abhängig seid.

## Ablauf
1. Kurze E-Mail mit Ausgangslage und Terminwunsch.
2. Erstgespräch (telefonisch oder vor Ort), dann klares Angebot.
3. Umsetzung oder Stellungnahme – in dem Umfang, den ein Nebengewerbe seriös leisten kann.

## Kontakt
- E-Mail: info@final-itb.de
- Telefon: 015678 520783
- Ort: Erlangen
```

Nicht reinschreiben: interne UKER-Teams, Förderakronyme ohne Mandat, „IT-Exzellenz“, leere Vortragstitel.

---

## Checkliste zum Abhaken

- [ ] Custom Domain `final-itb.de` mit HTTPS
- [ ] Impressum auf DDG, Datenschutz-Kopie dort entfernen
- [ ] Analytics entfernen **oder** Opt-in; Privacy-URL reparieren
- [ ] Datenschutzerklärung aktualisieren (nicht mehr 10/2023; Schweizer DSG nur falls nötig)
- [ ] AGB durch Dienstleistungs-AGB ersetzen oder Menüpunkt entfernen
- [ ] Vortragsseite mit echten Angaben oder aus der Nav nehmen
- [ ] Kontakt/Lebenslauf gegen aktuellen Stand prüfen
- [ ] Portrait ersetzen, Dateiname ohne `lowQuality`
- [ ] Startseite auf 3 Angebote + CTA umbauen
- [ ] Logo-Hotlinks entfernen oder lokal hosten
- [ ] Site-Sprache Deutsch, Search in der Navbar aus
- [ ] Meta-Title/Description setzen
