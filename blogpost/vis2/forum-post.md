
**VISUALISATION 3: REGIONAL EFFECT**

- **Map 1** — Each department is colored according to $η_{dpt}$, which conveys how much the local #1 name beats the national #1 name locally in the department $dpt$. High $η_{dpt}$ means strong regional naming identity.

$$\eta_{dpt} = \frac{|\text{local top name}|_{dpt}}{|\text{national top name}|_{dpt}} \geq 1$$

where $|p|_{dpt}$ is the number of births with the name $p$ in the department $dpt$.

- **Map 2** — When clicking on any department $R$ on Map 1, Map 2 is colored according to the $η_{k,S,R}$ metric (with $k=3$) to compare its naming culture to every other department $S$.

$$\eta_{k,S,R} = \frac{\sum_{i=1}^{k}|\text{i-th top name of } R|_R}{\sum_{i=1}^{k}|\text{i-th top name of } S|_R} \geq 1$$

$η_{k,S,R} \simeq 1$ → $R$ has a similar naming culture to $S$.  

$η_{k,S,R} \gg 1$ → $R$'s own names are much more popular there than $S$'s top names → very different cultures.

- **Decade slider** — Re-renders both maps for the selected decade.


**Research questions:**
- Is there a regional effect in naming data?
- Are some names more popular in specific departments?
- Are nationally popular names uniformly popular across France?

This visualisation answers these 3 questions by showing the most popular names for each department and the differences and similarities between the naming cultures of French departments, using color and user interactivity. 
The lack of color uniformity in the maps across certain departments in specific decades reveals a very clear regional effect in naming data. 
Map 1 emphasizes the departments that deviate from the national pattern (regarding the most popular name)—and thus answers the 3rd question—while Map 2 highlights the departments that deviate from the trend of the selected region (regarding the top-$k$ names); in both cases, the departments that diverge from the reference are colored in orange-red, a color that catches the eye right away. The tooltips that appear when hovering over departments reveal the top five names—and thus make it easy to answer the 2nd question—and give the exact number of births associated with each name as well as the proportion by gender.

**Strengths**
- The visualisation makes it easy to switch from a national baseline view to one based on the selected region, allowing users to identify similarities and differences between departments from different perspectives. 
- The inclusion of tooltips detailing the most popular first names, along with the number of births, the predominant gender and visual indicators (🔴/🔵), allows easy and instant reading of data details.
- The inclusion of the decade slider allows to see the regional effect in naming data over time.

**Weaknesses**
- The understanding of the visualisation may not be immediate as the metric is quite abstract and requires users to read carefully the formulas of $\eta_{dpt}$ and $η_{k,S,R}$.
- The $\eta$ metric is highly sensitive to the department size; in sparsely populated departments, even a small number of births is enough to cause significant variations in scores.
- The visualization mixes female and male names and does not reveal regional effects related to gender.
