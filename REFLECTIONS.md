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
(your own words)

## 7. Signal that the pipeline silently broke
(your own words)

## 8. Origin-city extension
(your own words)
