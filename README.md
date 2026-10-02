# Freight Cost Anomaly Detection and Carrier Pricing Analysis

A self directed analysis of 2,000 parcel shipments across seven carriers, looking for pricing anomalies that could point to overcharges or billing errors, and comparing which carriers give the best value for freight spend.

**Live dashboard:** [Tableau Public](https://public.tableau.com/app/profile/shivansh7419/vizzes)

## Why I built this

Freight is full of small pricing errors that quietly eat into margin. A shipment billed at twice the normal rate looks fine on its own, but across thousands of invoices it adds up. I wanted to see how many of these I could catch with nothing more than Excel and Tableau, and what a business could do about them.

## Tools

* **Excel** for cleaning, calculated fields, pivot tables and the anomaly flag
* **Tableau** for the dashboard and final visuals

## Dataset

[Dataset name and source link]

Each row is one shipment, with these fields:

| Field | Description |
|---|---|
| Shipment ID | Unique shipment reference |
| Shipment Date / Delivery Date | When the shipment left and arrived |
| Origin Warehouse / Destination | Route |
| Carrier | USPS, UPS, FedEx, DHL, OnTrac, LaserShip or Amazon Logistics |
| Status | Delivery status |
| Cost | Shipment cost |
| Weight kg | Shipment weight |
| Distance miles | Distance travelled |
| Transit Days | Days in transit |

## Method

1. **Cleaning.** [How you handled negative cost values and rows with no carrier recorded.]
2. **Calculated fields.** Added cost per kg (Cost ÷ Weight kg) and cost per mile (Cost ÷ Distance miles) for every shipment.
3. **Pivot tables.** Compared average cost per kg and per mile by carrier and by month before building any visuals.
4. **Anomaly flag.** Marked a shipment as an anomaly when [your rule].
5. **Dashboard.** Built the final views in Tableau and published them to Tableau Public.

## Key findings

**280 of 2,000 shipments (14%) were flagged as pricing anomalies.**

Anomaly rate by carrier:

| Carrier | Flagged | Total | Anomaly rate |
|---|---|---|---|
| DHL | 52 | 281 | 18.5% |
| FedEx | 49 | 295 | 16.6% |
| UPS | 40 | 256 | 15.6% |
| Amazon Logistics | 40 | 274 | 14.6% |
| OnTrac | 40 | 299 | 13.4% |
| LaserShip | 32 | 303 | 10.6% |
| USPS | 27 | 292 | 9.2% |

* **DHL had the highest anomaly rate**, roughly double USPS.
* **USPS was the best value carrier overall**, with the lowest cost per kg, the lowest cost per mile and the lowest anomaly rate.
* **Costs spike in peak months.** Average cost per kg reached $20.35 in January and $18.77 in July, about double the levels in September and December.

## Recommendations

1. **Move more volume to USPS**, since it is both the cheapest and the most consistently priced.
2. **Audit DHL and FedEx invoices more closely** before payment, as they carry the highest share of anomalies.
3. **Renegotiate peak season surcharges** with the highest cost carriers ahead of January, July and October.

**Bottom line:** shifting volume to USPS and checking DHL and FedEx invoices before payment is the quickest way to cut freight spend and stop overcharges.

## Limitations

* This is a public dataset, not real company data, so the findings show the approach rather than a live business result.
* The anomaly flag is a simple rule. A shipment can be flagged for a fair reason, such as an urgent or oversized delivery, so flagged shipments are candidates for review rather than confirmed errors.
* Costs are assumed to be in US dollars.

## Next steps

* Put a dollar value on the flagged shipments to estimate total potential overcharges.
* Add route level analysis to see whether anomalies cluster on particular lanes.

## Author

**Shivansh (Shiv) Pandey**
[LinkedIn](https://www.linkedin.com/in/shivansh-pandey-2312d/) · [Tableau Public](https://public.tableau.com/app/profile/shivansh7419/vizzes)
