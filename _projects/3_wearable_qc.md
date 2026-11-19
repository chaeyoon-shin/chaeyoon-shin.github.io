---
layout: page
title: Wearable Data QC
importance: 3
category: research
---

I handle preprocessing of our lab's wearable data (Samsung Galaxy Watch and continuous glucose monitors) and distribute analysis-ready master CSV files to lab members.

Main quality-control decisions:

- **Travel and time zones.** Records carry a time-zone label, and devices re-save past records under a new label after a time-zone change. Any day with a non-home label is dropped, together with 1 day before and 2 days after the trip, following evidence on travel-related sleep and circadian disruption ([Willoughby 2025](https://doi.org/10.1093/sleep/zsaf077){:target="_blank"}; [Li 2017](https://doi.org/10.1371/journal.pbio.2001402){:target="_blank"}; [Mattingly 2021](https://doi.org/10.1038/s41746-021-00435-2){:target="_blank"}).

- **Sleep nights.** Each main sleep is assigned to a noon-to-noon window, so a night belongs to the same date whether it starts before or after midnight ([van Hees 2018](https://doi.org/10.1038/s41598-018-31266-z){:target="_blank"}). Sessions that merge two nights, and nights without sleep-stage data, are handled separately.

<img src="{{ 'assets/img/wearable_qc/sleep_onset.png' | relative_url }}" alt="Distribution of main sleep onset times" style="width: 100%; max-width: 640px;">

- **Exercise heart rate.** Sessions shorter than 1 minute are not used for heart rate, because the first tens of seconds reflect the rapid cardiodynamic response rather than exercise intensity ([Lador 2008](https://doi.org/10.1152/ajpregu.00797.2007){:target="_blank"}).
- **Energy expenditure.** Daily totals outside 1,125–8,500 kcal are set to missing. The lower bound is the mean − 3 SD of doubly-labelled-water energy expenditure in Korean adults ([Kim 2017](https://doi.org/10.4162/nrp.2017.11.4.300){:target="_blank"}); the upper bound is the highest value measured in humans ([Westerterp 1986](https://doi.org/10.1152/jappl.1986.61.6.2162){:target="_blank"}).
- **CGM.** The first 72 hours of each sensor are dropped, and participants need at least 70% of possible readings, following international consensus ([Battelino 2019](https://doi.org/10.2337/dci19-0028){:target="_blank"}; [Battelino 2023](<https://doi.org/10.1016/S2213-8587(22)00319-9>){:target="_blank"}).

<img src="{{ 'assets/img/wearable_qc/cgm_warmup.png' | relative_url }}" alt="Share of CGM readings below 70 mg/dL by day since sensor start" style="width: 100%; max-width: 640px;">

- **Circadian rhythm.** The minimum daily heart-rate coverage (16 h) was chosen with a masking simulation on our own data, following the design of [Weed 2022](https://doi.org/10.3390/clockssleep4040039){:target="_blank"}. Features are computed in 14-day blocks so that participants with different record lengths are comparable; sleep regularity and chronotype follow [Phillips 2017](https://doi.org/10.1038/s41598-017-03171-4){:target="_blank"} and [Roenneberg 2004](https://doi.org/10.1016/j.cub.2004.11.039){:target="_blank"}.

<img src="{{ 'assets/img/wearable_qc/masking.png' | relative_url }}" alt="Masking simulation: accuracy and data retention by daily heart-rate coverage threshold" style="width: 100%; max-width: 640px;">
