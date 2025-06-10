# football-academy-matcher
Interactive tool that helps aspiring footballers identify top academies by analyzing player data, performance metrics, and market value predictions. Combines data science and visualization to highlight clubs that consistently develop elite talent.

My initial Pitch
https://docs.google.com/presentation/d/1kW6fJe4F3CduVDB96fMdaRJHZpJK4xlhaoBWz-MX658/edit?slide=id.p#slide=id.p

Chosen Database
https://www.kaggle.com/datasets/davidcariboo/player-scores/data

The Journey to Completion


Day 1 - Planning, Setup & Data Familiarization 

The day was split into two key phases. In the morning, I presented the project’s scope and vision to the team, outlining how we would utilize the available football transfer and player performance data to evaluate academy effectiveness. I also discussed potential limitations, such as incomplete data entries and ambiguity in transfer paths. 

Following this, I handled the technical setup by configuring IAM permissions in Google Cloud Platform, ensuring all team members had secure and appropriate access to the BigQuery dataset. 

In the afternoon, our focus shifted to data exploration and schema alignment. I guided the team through the database structure, explaining the relationships between key tables. Together, we performed initial SQL joins and began identifying which fields were essential to our analysis. This session helped build shared understanding and laid the groundwork for our cleaning and modelling approach. 


Day 2 - Data Cleaning, Early Integration & Roadblock Discovery 

Building on Day 1, we started the day with intensive work in BigQuery, writing SQL queries to begin the data cleaning process. We tackled inconsistencies, handled null values, and tested early joins to ensure key metrics like player movements, appearances, and market values aligned across tables. 

Later, we began integrating cleaned subsets into Looker Studio to test basic visualizations. This allowed us to evaluate how well the narrative would hold up in dashboard form. 

However, we encountered a major obstacle: messy data in the from_club_name and to_club_name columns. These fields are central to our aim of tracking player transitions (e.g. promotions to first teams or transfers between clubs), but were plagued with inconsistencies — shorthand naming, different spellings, and age group annotations like “U19”. 

To resolve this, I used REGEXP_REPLACE() in SQL to strip out recurring unwanted patterns, such as youth-team references. We also experimented with fuzzy matching (FuzzyWuzzy) to unify naming conventions, but the results were unreliable. Given the importance of accurate club names for our visual storytelling, we pivoted to a semi-manual cleaning process by exporting the dataset to Google Sheets. There, we began validating and normalising club names manually for consistency. 


Day 3: Finalising Data Cleaning & Early Dashboard Strategy 

We began the day by continuing the cleaning process, ensuring all club names and transfer-related fields were uniform and accurately matched. By midday, the cleaning was complete, and we performed a thorough inspection of the dataset. Encouragingly, clubs we had initially flagged as potentially high-value academies were indeed showing strong numbers in terms of player output and transfer value, confirming the reliability of our cleaned data. 

Next, we moved into dashboard planning in Looker Studio. At this stage, our goal was to stimulate team thinking around what stories the data could tell and what would be most useful to a target audience. We consolidated our cleaned datasets into a central “master table” — this table included summarised statistics for each player such as total appearances, goals, assists, cards, minutes played, and transfer value. 

We also tackled a nuanced data challenge: differentiating between players who were sold or loaned to other clubs versus those promoted to the first team. The from_club_name and to_club_name fields often used null values or ambiguous characters, so we had to manually investigate and reclassify these cases. In particular, we looked at players with a transfer_fee > 0 but missing an validated to_club_name, identifying hidden outbound transfers that required inclusion in our main visualisation logic. 


Day 4: Dashboard Conceptualisation & Design Build 

Day 4 was highly focused on Looker Studio and the visual side of our project. We shifted from raw analysis to crafting a narrative that would resonate with our end users. The central idea for the dashboard emerged clearly: a dynamic, interactive tool designed to help young players and their families make more informed decisions when considering offers from football academies. 

We envisioned the dashboard as a kind of “academy comparison engine,” where users could apply filters — such as position, nationality, or preferred foot— and receive insights into which academies best align with their aspirations based on recent data. 

To support this, we began prototyping character-based user journeys — hypothetical examples like a 15-year-old winger from France deciding between Lyon and PSG. These use-cases helped us validate the flow and utility of our dashboard. 

Meanwhile, with the cleaned master table now ready, we integrated it into a new Looker dashboard file that we intended to use as the final product. This marked a key transition in our project from data preparation to design execution. 

 

Day 5: Midpoint Demo & Predictive Modelling Exploration 

Day 5 marked our project’s demo day — an opportunity to share our progress and key insights with the wider cohort. I made it a priority to ensure each team member had time to present the area they contributed to, giving a full picture of the collaborative effort behind the project so far. 

During the demo, I outlined our roadmap for the final week, highlighting both our technical goals and our vision for refining the dashboard’s user experience. 

In parallel, I began experimenting with predictive modelling using linear regression. The aim was to estimate the maximum potential market value of academy players based on available performance and development metrics. In addition to this, I used the same approach to assess the average time a player spends at a club before being promoted to the first team or transferred out — a crucial data point for our intended audience. 

Initial results have been highly promising and align well with our broader story: providing actionable, data-driven insights into player development pathways. Once we finalise the visual placement and context, these models will be integrated into our dashboard in the coming week to enhance its impact and interactivity. 

 

Week 2 Day 6 

Today began with a brief morning meeting to outline the day’s objectives and align the team. The primary focus was selecting a suitable theme and complementary color palette for the dashboard. This was completed efficiently, allowing us to shift our attention to exploring additional academy-related KPIs to enhance the dashboard’s value. 

Once the key visual and data elements were locked in, we proceeded with initial final touches—refining layout choices, improving visual consistency, and addressing various cosmetic adjustments to ensure a polished, user-friendly interface. 

The overall goal for today was to set the stage for tomorrow’s focus on narrative development. As such, we wrapped up by preparing the dashboard for presentation scripting, which will help emphasize the storytelling aspect of our work. In addition, we plan to reassess the current KPI set tomorrow and identify any final enhancements or refinements. 

The team continues to collaborate effectively, which has made my responsibilities as team leader both manageable and rewarding. 

 

Week 2 Day 7 

We began the day with a quick team recap, realigning on our progress and next steps. A key decision was assigning one team member responsibility for maintaining a consistent color scheme across all dashboards to reinforce the cohesive, product-like feel we’re aiming for. 

I created a SQL table that tracks rolling totals for academy player promotions by club, which enabled the development of a dynamic car race chart visualizing this data. Much of the day was spent fine-tuning visual elements and ensuring consistency across dashboards, with the understanding that some additional refinement may still be needed in the coming days. 

Initial scripting work for the presentation also began today, setting up the narrative structure that will guide viewers through our insights. The team continues to collaborate smoothly, and we’re progressing well toward a polished, storytelling-driven final product. 

 

Week 2 Day 8 

We kicked off the day with a team meeting, creating space for open discussion and ensuring alignment on the project narrative—especially as script writing progressed. One key improvement was simplifying our introduction page, which had previously been too text-heavy. We replaced it with a visual diagram built using Flourish to more effectively communicate the core problem. 

The team continued refining the dashboard, with a strong focus on visual polish and clarity. With the script nearing completion, we conducted our first round of trial runs, keeping a close eye on timing and flow. The initial results were promising, and while further revisions and rehearsals are planned, we're confident in the direction we're heading and the time we have left to perfect the final delivery. 


Week 2 Day 9 

We kicked off today with a clear briefing to align on our objectives and priorities for the final stretch. Shortly after, we jumped into a timed dry run of our pitch presentation to assess pacing, content delivery, and transitions. Today’s focus was firmly on rehearsals and refining the narrative—stripping the script back to its essentials and ensuring every word served the story we were trying to tell. 

A major goal was to streamline our pitch and clearly communicate our value proposition. By midday, we had locked in a strong draft of the final script, freeing up the afternoon for further run-throughs and polish. This included tightening transitions between speakers and refining the interactivity of our dashboard demo to ensure a smooth, professional user experience. 

One of the most satisfying moments came when we saw just how much the dashboard had evolved—not only in terms of aesthetics, but also in how powerfully it conveyed insights. The interactivity and real-world utility of the tool stood out, and I could genuinely see how it could support aspiring footballers and their families in making more informed decisions. 

Tomorrow is the big day—final project pitch day. It's an opportunity to showcase our work to the rest of the cohort and bring everything together. Personally, this journey has been deeply rewarding. Leading the team has pushed me to grow both technically and creatively. From coding and data storytelling to managing a team through rapid iterations, it’s been a truly transformative experience. 
