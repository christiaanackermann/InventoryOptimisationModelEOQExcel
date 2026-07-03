# 📦 Inventory Optimisation Model — EOQ & Safety Stock

An Excel-based inventory optimisation model that applies **Economic Order Quantity (EOQ)**, **safety stock**, and **ABC classification** to real transactional retail data to minimise total inventory cost and recommend data-driven procurement decisions.

Built entirely in Excel with live formulas — no macros, no add-ins. Open it and every figure recalculates from the raw data.

---

## 🎯 What it does

The model takes a year of invoice-level sales data, aggregates it by SKU, and computes the optimal ordering policy for each item:

- **Economic Order Quantity (EOQ)** — the order size that minimises combined holding and ordering costs
- **Safety stock** — a demand-variability buffer sized to a target service level
- **Reorder point** — the inventory level that triggers a new order
- **ABC classification** — ranks SKUs by cumulative cost impact so attention goes where it matters
- **Baseline vs. optimised comparison** — quantifies the cost saving from switching to EOQ-driven ordering

---

## 📊 Workbook structure

| Sheet | Purpose |
|-------|---------|
| **Executive_Dashboard** | Headline metrics, ABC breakdown, top A-items by cost impact, and management recommendations |
| **Assumptions_Sheet** | Data sources, cost parameters, formula definitions, and stated model limitations |
| **DataSetRaw** | Raw invoice transaction data (SKU, quantity, date, price, country, customer) |
| **SKUAnalysis** | Per-SKU aggregation — total quantity, order count, demand standard deviation, and revenue |
| **Inventory_Model** | Core engine: EOQ, safety stock, reorder point, annual holding/ordering costs, and ABC category per SKU |
| **Baseline_EOQ_Analysis** | Baseline cost vs. optimised cost, with per-SKU and total savings |

---

## 🧮 Methodology

| Metric | Formula |
|--------|---------|
| Economic Order Quantity | `EOQ = √(2·D·S / H)` |
| Safety Stock | `SS = Z · σ · √(LT)` |
| Reorder Point | `ROP = (Daily Demand · LT) + SS` |
| Annual Holding Cost | `(EOQ / 2) · H` |
| Annual Ordering Cost | `(D / EOQ) · S` |

Where **D** = annual demand, **S** = cost per order, **H** = holding cost per unit, **Z** = service-level factor, **σ** = demand standard deviation, **LT** = lead time.

---

## ⚙️ Key assumptions

- **Holding cost rate:** 25% of unit value (industry standard estimate)
- **Cost per order:** $100 fixed
- **Lead time:** 7 days (assumed constant)
- **Service level:** 95% (Z = 1.65)
- **Data period:** ~1 year (2024 invoice records)
- **Scope:** 44 SKUs with 2+ transactions, drawn from 103 individual purchases

---

## 📈 Sample output

- **44 SKUs** analysed and classified
- Per-SKU EOQ, safety stock, and reorder points generated automatically
- Top A-items surfaced by cost impact for priority review
- Baseline-vs-optimised savings quantified across the catalogue

---

## ⚠️ Limitations

The model is deliberately transparent about its simplifications:

- Holding cost rate (25%) is an estimate and varies by product in practice
- Lead time is treated as constant; real supplier lead times fluctuate
- Demand is assumed normally distributed — seasonality is not modelled
- Supplier/bulk volume discounts are not included
- Stock-out costs are excluded from the trade-off analysis
- Warehouse storage is assumed unlimited

---

## 🚀 How to use

1. Open the workbook in Excel (or a compatible spreadsheet app).
2. Replace the contents of **DataSetRaw** with your own invoice data (keep the column layout).
3. Adjust the parameters in **Assumptions_Sheet** (holding rate, order cost, lead time, service level) to match your business.
4. Review recomputed EOQ, reorder points, and savings on the **Inventory_Model** and **Executive_Dashboard** sheets.

---

## 🏷️ Suggested repo topics

`inventory-management` · `eoq` · `safety-stock` · `abc-analysis` · `supply-chain` · `excel` · `operations-research` · `demand-forecasting`

---

**Author:** Christiaan Ackermann
