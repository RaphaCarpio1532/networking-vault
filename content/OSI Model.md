---
tags: [fundamentals, model]
---
up:: [[01 Networking Fundamentals]]
# OSI Model

## 🇬🇧 English
A 7-layer conceptual model describing how data travels across a network. Top to bottom: **Application, Presentation, Session, Transport, Network, Data Link, Physical**. Memorize: "All People Seem To Need Data Processing." Each layer has its own protocols and its own attacks, so it is the mental map for troubleshooting and security.

Key layers for help desk:
- **Layer 7 Application** – HTTP, DNS, SMTP.
- **Layer 4 Transport** – TCP/UDP, [[Ports and Protocols]].
- **Layer 3 Network** – IP, [[Routers]], [[IP Addressing]].
- **Layer 2 Data Link** – [[MAC Address]], [[Switches]], [[ARP]].
- **Layer 1 Physical** – cables, signals.

## 🇮🇹 Italiano
Un modello concettuale a 7 livelli che descrive come i dati viaggiano in rete: **Applicazione, Presentazione, Sessione, Trasporto, Rete, Collegamento dati, Fisico**. Ogni livello ha i suoi protocolli e i suoi attacchi, quindi è la mappa mentale per il troubleshooting e la sicurezza.

## Related / Correlati
- [[TCP-IP Model]]
- [[Packets and Frames]]
- [[Ports and Protocols]]
