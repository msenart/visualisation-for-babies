# **Visualization 2:**

## Task

- Is there a regional effect in the data?
- Are some names more popular in some regions?
- Are popular names generally popular across the whole country?

## Our visualisation

We will implement (if Altair allows it) to implement a Visualisation constituted of two maps. **The first one ** is a map of France, in which **the departments are coloured** according to a certain number that tells about how is the global name ranking different from the regional name ranking. For example, we could have :
$$
\eta_{region} = \frac{|\text{most famous name in the region}|_{region}}{|\text{most famous name in the country}|_{region}} \geq 1
$$

Or we can apply that logic for the top k-names in the region :

$$
\eta_{k,region} = \frac{\sum_{i=1}^{k}|\text{i-st most famous name in the region}|_{region}}{\sum_{i=1}^{10}|\text{i-st most famous name in the country}|_{region}} \geq 1
$$
Where $||_{region}$ is like doing the SQL operation ``SELECT COUNT * FROM table WHERE region = "region"``.

The higher the $\eta$ is (one meaning that the regional ranking is exactly the same as theglobal ranking), the more the region is coloured, meaning that the region doesn't match with the global ranking, that there is discrepancies between **the local top and the global top**.

When **hovering** on a specific region, the user will we able to see the top k-names of the region (presented with other infos, such as the number of people with the name, the genre percentage (60%M/40%F), etc...)

When the user **clicks** on :

- a specific name of the region ranking, the user will see **a second map** of France, but coloured with another ratio of the people having that specific name. This ratio could be : $$
\omega_{name} = \frac{|\text{number of people having the name in the region}|_{region}}{|\text{total number of people in the region}|_{region}}$$ Or :$$
\omega_{name} = \frac{|\text{number of people having the name in the region}|_{region}}{|\text{number of people having the name in France}|_{France}}$$

- on the region, it compares the selected region ranking to all the other region rankings along a similar metric $\eta_{k,region}$ : 

$$
\eta_{k,\text{selected region},region} = \frac{\sum_{i=1}^{k}|\text{i-st most famous name in the region}|_{region}}{\sum_{i=1}^{10}|\text{i-st most famous name in the selected region}|_{region}} \geq 1
$$

It is two interesting different behaviors under discussion, we will select only one of them.

Finally, to complete the map, we could add a **chronological slidebar**, that makes the average on X-years (X could be represented by the length of the sliderbar) to capture time tendencies.



## Pros :

- Solid comparator to see regional discrepancies to the global ranking.
- Local region comparator to see discrepancies. 

## Cons :

- might be a demanding implementation for Altair.
- Completely ignores the name of minority peoples (we could invert the logic though).
