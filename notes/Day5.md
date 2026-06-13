# Day 5 - COVID-19 EDA: Investigating Factors Behind COVID Mortality

## Objective

After analyzing continent-level trends, today's goal was to understand which country-level factors might be associated with COVID deaths per million.

Instead of focusing on cases and deaths alone, I explored demographic, economic, and healthcare-related variables to identify possible explanations for differences in mortality across countries.

---

## Life Expectancy vs Deaths per Million

### Analysis

I created a country-level dataset containing:

- Life Expectancy
- Maximum Deaths per Million

and visualized their relationship using a scatter plot.

### Observation

- Countries with higher life expectancy generally showed higher deaths per million.
- This initially seemed counterintuitive because countries with higher life expectancy are often more developed.
- A possible explanation is that countries with higher life expectancy tend to have larger elderly populations, making them more vulnerable to severe COVID outcomes.

### Limitation

- Life expectancy itself is not the direct cause of higher mortality.
- It may simply act as an indirect indicator of population age structure and demographic characteristics.

---

## Median Age vs Deaths per Million

### Analysis

To test whether age structure was actually driving the previous observation, I analyzed:

- Median Age
- Deaths per Million

### Observation

- A clear positive trend was observed.
- Countries with higher median age generally experienced higher COVID mortality.
- Compared to life expectancy, median age provided a much more direct explanation of mortality differences.

### Insight

This supports the idea that older populations were more vulnerable to severe COVID infections and complications.

---

## GDP per Capita vs Deaths per Million

### Analysis

I explored whether economically stronger countries experienced lower mortality.

### Observation

- GDP per capita did not show a strong or consistent relationship with deaths per million.
- Countries with similar GDP levels often exhibited very different mortality outcomes.
- This suggests that economic strength alone cannot explain COVID mortality.

### Insight

A country's wealth may improve healthcare infrastructure, but mortality outcomes depend on multiple interacting factors.

---

## GDP per Capita vs Handwashing Facilities

### Analysis

To understand how economic development influences public health infrastructure, I examined:

- GDP per Capita
- Handwashing Facilities

A LOWESS trend line was used to reveal the underlying pattern.

### Observation

- A strong positive relationship was observed.
- Countries with higher GDP generally had greater access to handwashing facilities.
- The trend eventually approached near-universal coverage in high-income countries.

### Insight

Economic development appears to play a significant role in improving sanitation infrastructure.

---

## GDP per Capita vs Hospital Beds per Thousand

### Analysis

I investigated whether wealthier countries tend to have better healthcare capacity.

### Observation

- GDP showed a positive relationship with hospital-bed availability.
- However, the relationship was weaker and more variable than the relationship with handwashing facilities.
- Countries with similar GDP levels often had noticeably different numbers of hospital beds.

### Insight

Healthcare infrastructure is influenced not only by economic strength but also by healthcare policies and national priorities.

---

## Binning Analysis

### Concept Learned

Today I learned how to use:

```python
pd.cut()
pd.qcut()
