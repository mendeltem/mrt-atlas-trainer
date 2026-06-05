# MRT-Atlas Trainer 🧠🔬

Ein interaktives Web-Tool für Neurowissenschaften- und Medizinstudierende, um die strukturelle Anatomie des menschlichen Gehirns spielerisch und hocheffizient zu erlernen. 

👉 **[Hier direkt im Browser spielen!](https://mendeltem.github.io/mrt-atlas-trainer/)**

---

## 🚀 Features

* **Interaktiver MRT-Schnittbild-Viewer:** Nahtloses Blättere durch die verschiedenen Gehirnschichten (Schichten 1–32) mithilfe von Schiebereglern, dem Mausrad oder den Pfeiltasten (wie in `grafik_2.jpg` zu sehen).
* **AAL-Atlas Overlay:** Ein präzises, farbiges Overlay im MNI-Standardraum visualisiert die exakten anatomischen Regionen (Automated Anatomical Labeling).
* **Zwei interaktive Modi:**
  * **Erkunden:** Klicke auf eine beliebige Stelle im Schnittbild, um sofort den exakten Regionsnamen (Deutsch + AAL) und dessen Funktion zu sehen. Mit dem "Atlas"-Regler lässt sich die Farbe stufenlos ein- und ausblenden, um die darunterliegende T1-Struktur zu analysieren.
  * **Training:** Teste dein Wissen! Das Tool fordert dich auf, bestimmte Gehirnregionen selbstständig zu finden und anzuklicken.

---

## 🛠️ Technische Umsetzung & Pipeline

Das Projekt ist so optimiert, dass es vollständig clientseitig im Browser läuft – ohne Datenbanken oder schwere Server-Infrastruktur:

1. **Python-Preprocessing:** Die zugrundeliegenden 3D-MRT-Daten (MNI152 T1) und die dazugehörigen Atlas-Labels wurden vorab in Python verarbeitet und in hochoptimierte, verlustfreie 2D-Bildschichten exportiert.
2. **Pixel-perfekte Klick-Erkennung:** Die Zuordnung der Mausklicks zu den anatomischen Regionen erfolgt über eine im Hintergrund geladene, unsichtbare Farb-Label-Karte. Jeder Pixel-Farbwert korrespondiert dabei exakt mit einer AAL-ID.
3. **Web-Stack:** Reines HTML5, CSS3 (Dunkelmodus für augenschonendes Lernen) und natives JavaScript für die UI-Steuerung.

---

## 🔬 Wissenschaftlicher Hintergrund & Validierung

Dieses Tool wurde im Kontext neuroimaging-basierter Forschung entwickelt. Die zugrundeliegende Bildpipeline und die Segmentierungsgenauigkeit basieren auf methodischen Validierungen, die unter anderem an einem Datensatz von **94 Patienten** evaluiert wurden. Der Fokus liegt hierbei auf der präzisen anatomischen Zuordnung im standardisierten MNI-Raum, um eine Brücke zwischen theoretischer Neuroanatomie und praktischer MRT-Auswertung zu schlagen.

---

## 📖 Effektive Lernstrategie (Empfehlung für Studierende)

Für den maximalen Lernerfolg empfehlen wir folgendes Vorgehen:

1. **Visuelle Orientierung:** Nutze zuerst den **Erkunden-Modus**. Fahre mit der Maus über markante Strukturen (z. B. den Thalamus oder Nucleus caudatus in Schicht 17) und präge dir die anatomischen Nachbarschaften ein.
2. **Strukturen isolieren:** Nutze den **Atlas-Regler**, um das farbige Overlay langsam auszublenden. Versuche, die Grenzen der Regionen allein anhand der Graustufen des T1-Bildes zu erkennen.
3. **Selbsteinschätzung:** Wechsle in den **Training-Modus** und versuche, die abgefragten Regionen ohne Hilfsmittel in verschiedenen Schichten zu finden.

---

## 🤝 Feedback & Mitwirken

Wenn du Fehler in den Regionsbezeichnungen findest, Feedback zur Usability hast oder neue Features vorschlagen möchtest, öffne gerne ein **Issue** oder erstelle einen **Pull Request**!
