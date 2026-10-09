# Comisiones

At the optician's where I work, our commission depends on who made each sale. The billing system says who *charged* each invoice, but we share users, so sometimes a sale ends up under the wrong name. Every month we printed all the invoices and sorted them by hand to fix that.

This page does it instead. You load the month's invoice report (the CSV export from the billing system), go through the invoices one by one, and press **D** or **C** to say who really sold it. The totals and commissions update as you go.

Everything runs in the browser. The CSV is read on your own computer and never uploaded anywhere.

## Try it

Open `mockups/comisiones.html` in a browser and load `ejemplo/facturas-septiembre-ejemplo.csv`. That file is made up (fake patients, fake invoice numbers) but has the same columns and format as the real export.

The first time you use it with real data, open **Ajustes** and put in each person's name and their user exactly as it shows in the "COBRADO POR" column. That stays in your browser only, so no names are in the code.

## The rules it uses

- Total for the month = every invoice, with IVA.
- If the clinic passes 30.000.000 Gs that month, everybody gets 6%. If not, 5%.
- Commission = (your sales ÷ 1,10) × the rate. The ÷ 1,10 takes the 10% IVA out.

I checked this against a real month's pay and it matched to the guaraní.

## When you're done

"Guardar resultado" gives you three ways to hand it over:

- **PDF**: each person's commission, system vs. corrected, and the list of invoices you changed.
- **Excel**: the same report the system exported, with two extra columns (who it ended up as, and whether you changed it). You can load it back into the page later.
- **The page itself**: a single .html file with your corrections inside. Double-click it on any computer.

Your progress is also saved in the browser while you work, so closing the tab doesn't lose anything.

## What's in here

```
mockups/comisiones.html   the working version (the one I actually use right now)
ejemplo/                  a fake month to try it with
app/                      my own rebuild, written from scratch as practice (in progress)
guia/                     CSS snippets I reuse
```

No build step, no dependencies. Just the HTML file.
