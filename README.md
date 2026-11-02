# UK fuel prices: daily averages, postcode areas and stale prices

The UK average pump price for standard unleaded (E10) and diesel (B7), one row a day from 24 September 2026, plus the average price in each postcode area and the share of forecourts whose price has not moved in 14 or 30 days. Figures come from Fuel Finder, the UK government service every forecourt must report its price changes to. This copy was taken on 2 November 2026 from the 06:20 (UK time) snapshot.

## Files

| File | What it holds |
|---|---|
| `data/daily-average.csv` | One row per day (UK time) from 24 September to 1 November 2026: the total station count, the station count for each fuel, and the mean (`_average_p`) and median (`_median_p`) price for E10 and B7. Each row is the last snapshot of that day. There is no row for 24 October 2026. 2 November is left out because the day was incomplete when the copy was taken. |
| `data/postcode-areas-2026-11-02.csv` | For each postcode area (the letters at the start of a postcode, such as LS or BT) with at least 5 stations selling the fuel: station count, mean, median, cheapest and dearest price, ranked from the lowest mean. 119 areas for E10 and 119 for B7. |
| `data/stale-prices-2026-11-02.csv` | The number and share of Fuel Finder stations with no price update in over 14 days and in over 30 days, for all stations and for each brand with 10 or more stations. |
| `data/uk-fuel-prices.json` | The three tables in one file, with the source page and the date they were read. |

Prices are in pence a litre. Means and medians are taken across stations and are not weighted by sales, so they describe the stations covered. They are not an official price index.

## What the numbers say

From 24 September to 1 November 2026 the mean E10 price went from 173.6p to 172.1p and diesel from 198.2p to 198.7p. On 2 November the BT postcode area (Belfast, which covers all of Northern Ireland) had the lowest mean for both fuels, at 164.7p for E10 and 191.1p for diesel. Telford (TF) was the dearest for E10 at 176.7p, and the Outer Hebrides (HS) the dearest for diesel at 208.9p. Of 8,073 Fuel Finder stations, 1,918 (23.8%) had not changed any price in over 14 days and 766 (9.5%) in over 30 days.

## How it was made

Prices are downloaded from Fuel Finder every 5 minutes. On 2 November, 8,073 of the 8,151 stations came from Fuel Finder and 78 from open retailer price feeds (Asda, SGN and Esso) for forecourts Fuel Finder does not list yet. Where both list a forecourt, the Fuel Finder price is used. Closed forecourts and prices outside 90p to 300p a litre are left out.

The station count falls from 8,313 on 25 September to 8,156 on 26 September because, from that day, 157 forecourts listed by both Fuel Finder and a retailer feed were counted once. It was also higher on 2 and 3 October (8,314 and 8,315), so treat small price moves around those days with care.

A station counts as stale when its most recent price update, across all its fuels, is more than 14 (or 30) days old. Fuel Finder keeps a price until the forecourt reports a new one, so an old price may still be the pump price.

## Source and licence

Compiled by Rai Ansar for [fuelprices.org.uk](https://fuelprices.org.uk/fuel-price-tracker/), where the area and stale-price tables refresh with every snapshot and the daily table gains a row each day. This repository is the 2 November 2026 copy and is not updated.

Fuel price and forecourt data from Fuel Finder: contains public sector information licensed under the Open Government Licence v3.0. These files are shared under the same licence: you may copy and reuse them with a link to fuelprices.org.uk and the date of the figures you use.
