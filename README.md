# Kundensegmentierung mit Unsupervised Learning

Dieses Projekt zeigt, wie Kunden eines Einzelhandelsunternehmens anhand ihres Kaufverhaltens in Gruppen eingeteilt werden können. Ziel ist es, gezielte Marketingstrategien für unterschiedliche Kundensegmente zu entwickeln.

---

## Datensatz

Der Datensatz enthält historische Online- und Offline-Käufe von Kunden.

**Wichtige Spalten:**

- `CUST_ID` – Kundennummer  
- `PURCHASE_CHANNEL` – Kanal der Bestellung  
- `RECENT_CHANNEL` – letzter Kaufkanal  
- `FIRST_PURCHASE_DATE` / `LAST_PURCHASE_DATE` – Kaufdaten  
- `NUM_ORDERS_ONLINE` / `NUM_ORDERS_OFFLINE` – Bestellanzahl  
- `SPEND_OFFLINE_TOTAL` / `SPEND_ONLINE_TOTAL` – Ausgaben  
- `CATEGORIES_LAST12` – Kategorien der letzten 12 Monate  
- `RECENCY` – Tage seit letztem Kauf  
- `TENURE` – Kundendauer  
- `MONETARY` – Gesamtausgaben  
- `FREQUENCY` – Gesamtanzahl Käufe  

---

## Feature Engineering

- Berechnung von `Recency`, `Tenure`, `Monetary`, `Frequency`  
- Skalierung numerischer Daten mit `MinMaxScaler` (0–1)  

---

## Clustering-Methoden

### K-Means

- Optimale Clusteranzahl über die **Elbow Method** bestimmt  
- Segmentierung nach RFM-Kriterien  

**Beispiel-Insights:**  
- **Cluster 1:** Neue oder seltene Käufer → Marketingaktionen zur Aktivierung  
- **Cluster 3 & 5:** Aktive, treue Kunden → gezielte Angebote, Treueprogramme  
- **Cluster 6:** Ehemalige Kunden → Rückgewinnungskampagnen  

### Hierarchisches Clustering

- Linkage-Methode: `average`  
- Dendrogramm zur Erkennung von Ausreißern  

**Beispiel-Insights:**  
- Große Cluster (1,2,6): regelmäßige Kunden → Marketingmaßnahmen sinnvoll  
- Cluster 3: Inaktive Kunden → Rückgewinnungskampagnen  
- Cluster 4 & 5: Ausreißer → evtl. ausgeschlossen  

---

## Empfehlung

- **Marketingaktionen:** auf mittlere und aktive Cluster fokussieren  
- **Rückgewinnung:** inaktive oder verlorene Kunden gezielt ansprechen  
- **Ausreißer:** nicht für Standardanalysen verwenden  
