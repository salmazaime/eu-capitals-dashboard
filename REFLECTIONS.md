# Reflections

## 1. Before building: weather vs CO2
I would weigh weather a bit more, maybe 60/40.

## 2. Batched API call vs 26 calls
One request means one connection so only one chance to time out or get throttled. 26 separate connections from a shared GitHub runner IP gives 26 chances to fail (+ a failure halfway leaves you with incomplete data). So it's more reliable not just faster.

## 3. The CO2 emissions factor
Before publishing i wouldd check the 0.15 figure against a current official source (DEFRA or ADEME) + show the source on the page and say clearly that its an estimate. Ideally I would also use different factors for short and long flights.

## 4. Normalization: KPI vs raw measurement
A raw measurement is absolute, while a KPI is a constructed number that depends on the list and on my choices.

## 5. Predicted winner
Madrid because its warm and sunny, and not too far from Paris. 

## 6. Prediction vs real result
My prediction was Madrid, the result was Madrid, weather score 0.80, CO₂ score 0.77 (273.8 kg CO₂e round trip, 912.5 km each way).


## 7. Signal that the pipeline silently broke
There is a "data last updated" line at the bottom of the page. So if the date is weeks old instead of this Monday then a visitor can tell the schedule stopped/keeps failing, without opening the Actions tab. Its not good enough on its own, because nobody reads that tiny grey line. I would maybe add a visible warning banner when the data is older than about 8 days.

## 8. Origin-city extension
I changed 2 files. In fetch_and_score.py i replaced the origin coordinates with Lyon's and changed the exclusion line to dest_rows = rows, since Lyon isn't in the CSV and there was nothing to exclude. In index.html I replaced "from Paris" with "from Lyon" and updated the chart title from 26 to 27 destinations. Those were the right places because the origin is hardcoded there, and the data and the page both depend on it. The best destination isnt an absolute fact about these capitals. It depends on where you start because distance changes every CO₂ score, and that can change the winner.
