---
layout: page
title: Wearable Data QC
importance: 3
category: research
---

I built and maintain our lab's wearable data pipeline (Samsung Galaxy Watch, continuous glucose monitors), from raw exports to analysis-ready tables.

- **Database.** Monthly raw Samsung Health exports are loaded into MongoDB by a weekly scheduled job, keeping every record as exported.
- **Master CSV.** When new data arrive, a QC pipeline rebuilds three tables (daily features, per-participant CGM summary, per-participant circadian rhythm) into a dated folder.
- **Documentation.** I wrote a lab guide covering the pipeline schedule and paths, how to query and export the database for first-time users, and the preprocessing rule and rationale for every variable, with a checklist for analysts.

Some examples of quality-control decisions:

- **Travel and time zones.** Travel is detected from the time-zone label on each record. Exports contain copies of pre-departure records under the destination's label (same clock time, same value), and a few records carry a spurious UTC label; neither counts as travel. Departure and return days, which mix two time zones, are dropped. Days abroad and 1 day before / 2 days after a trip are kept with flags so analysts can decide, following evidence on travel-related sleep and circadian disruption ([Willoughby 2025](https://doi.org/10.1093/sleep/zsaf077){:target="_blank"}; [Li 2017](https://doi.org/10.1371/journal.pbio.2001402){:target="_blank"}; [Mattingly 2021](https://doi.org/10.1038/s41746-021-00435-2){:target="_blank"}).

- **Sleep nights.** Each main sleep is assigned to a noon-to-noon window, so a night belongs to the same date whether it starts before or after midnight ([van Hees 2018](https://doi.org/10.1038/s41598-018-31266-z){:target="_blank"}). Sessions that merge two nights, and nights without sleep-stage data, are handled separately.

<img src="{{ 'assets/img/wearable_qc/sleep_onset.png' | relative_url }}" alt="Distribution of main sleep onset times" style="width: 100%; max-width: 640px;">

- **Exercise heart rate.** Sessions shorter than 1 minute are not used for heart rate, because the first tens of seconds reflect the rapid cardiodynamic response rather than exercise intensity ([Lador 2008](https://doi.org/10.1152/ajpregu.00797.2007){:target="_blank"}).
- **Wear time.** Steps cannot show whether the watch was worn, because the phone also counts steps. Daily wear time is estimated as hours with any heart-rate record and was validated against the watch's own on/off-body events (97% of days with at least 10 estimated hours were truly worn at least 10 hours), so analysts can apply a valid-day rule.
- **Energy expenditure.** Daily totals outside 800–8,500 kcal are set to missing. A day cannot fall below basal metabolic rate: the lower bound is the lowest Mifflin–St Jeor estimate in our cohort, from clinic-measured height and weight, minus the equation's ±10% error ([Frankenfield 2005](https://doi.org/10.1016/j.jada.2005.02.005){:target="_blank"}); the upper bound is the highest value measured in humans ([Westerterp 1986](https://doi.org/10.1152/jappl.1986.61.6.2162){:target="_blank"}).
- **CGM.** The first 72 hours of each sensor are dropped, and participants need at least 70% of possible readings, following international consensus ([Battelino 2019](https://doi.org/10.2337/dci19-0028){:target="_blank"}; [Battelino 2023](<https://doi.org/10.1016/S2213-8587(22)00319-9>){:target="_blank"}).

<img src="{{ 'assets/img/wearable_qc/cgm_warmup.png' | relative_url }}" alt="Share of CGM readings below 70 mg/dL by day since sensor start" style="width: 100%; max-width: 640px;">

- **Circadian rhythm.** The minimum daily heart-rate coverage (16 h) was chosen with a masking simulation on our own data, following the design of [Weed 2022](https://doi.org/10.3390/clockssleep4040039){:target="_blank"}. Features are computed in 14-day blocks so that participants with different record lengths are comparable; sleep regularity and chronotype follow [Phillips 2017](https://doi.org/10.1038/s41598-017-03171-4){:target="_blank"} and [Roenneberg 2004](https://doi.org/10.1016/j.cub.2004.11.039){:target="_blank"}.

<img src="{{ 'assets/img/wearable_qc/masking.png' | relative_url }}" alt="Masking simulation: accuracy and data retention by daily heart-rate coverage threshold" style="width: 100%; max-width: 640px;">
