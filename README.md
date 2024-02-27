# Mental Health in the Tech Industry Survey Analysis 

## Foreground

    The analysis concerns a mental health study that has been enacted through 2014-2019 (skipping the year 2015). The survey was conducted globally in 79 countries, but mainly in the `United States`, `United Kingdom` & `Canada`. The survey had several question types:
        * free-form questions - they mainly concern asking for experiences that people had with their or others' mental health situations.
        * Participant information questions - user defining questions such as `race`, `age`, `whether they work in a tech organization`, etc.
        * Ranking-based questions - questions concerning ranking different experiences or beliefs on a 1-10 or 0-1 (boolean) rating systems. 

The analysis dives deep into the distribution of ranking based questions over the years to pull out interesting findings of changes throughout the years.

## Table of Contents

* Data Preparation
* Initial Analysis
* Exploratory Data Analysis
* Conclusions
* Improvement Points

## Tables Used

The dataset used for this analysis comes from a sqlite database of `three tables`:

`Answer` table:
* `UserID` - Value that identifies a unique participant in the dataset
* `SurveyID` - Foreign key of a survey that was shown to the `UserID` used to link to the `Survey` table
* `QuestionID` - Foreign key of a question that was shown to the `UserID` used to link to the `Question` table
* `Answertext` - Answer that was given to a `Question` by a `UserID` during the `Survey`

`Question` table:
* `Question` - Primary key used to link each question to the `Answer` table
* `Questiontext` - the question that is portrayed in the survey to participants

`Survey` table:
* `SurveyID` - Primary key used to link each survey to the `Answer` table
* `Description` - the survey that was given to the participants

The tables are thus linked in this format:
* `SurveyID` (Primary Key in `Survey`) <===> `SurveyID` (Foreign Key in `Answer`)
* `QuestionID` (Primary Key in `Question`) <===> `QuestionID` (Foreign Key in `Answer`)


## Conclusions made: 
* The number of participants have been steadily decreasing, although the number of total questions asked has shot up.
* Percentage-wise, `~30%` of all questions are not responded to each year (again, except for `2014`).
* Most popular organizations have actually more than `1000 employees`, then we have it being followed by `26-100`, `100-500`, `6-25`, `1-5` & `500-1000`.
* Most respondents live in the `United States`, the `United Kingdom` or `Canada`. In terms of `US states`, there was a quite wide geographic distribution range for respondents, however most responses came from `California`, `Washington`, `New York` & `Illinois`. The other biggest continent in terms of responses was `Europe`, with `Germany` & the `Netherlands` leading the way.
* Around `68.5%` of companies that our respondents work in, work in tech orgnanizations, whereas ~20% seem to be working not for a tech organization. 
* `White` participants in terms of race seem to be dominating all responses, with all other races combined only have approximately `7.5%` of all responses made to the surveys in total.
* `42%` of all employees reported having mental health disorders throughout the 4 years of survey analysis. `~22% `of all respondents report that they possibly/maybe have a Mental Health Disorder.
* The survey conducted in 2014 generated the most amount of participation as a sizeable amount of all participants answered all questions to the survey. Later years were not as successful, with the next biggest fulfillment rate for a survey peaking `88.2%`. The top respondents in terms of fulfillment rate were: `4068`, `4071`, `3711`, `3414` & `2786`. However, their surveys, compared to the surveys made in 2014, had many more questions (2017, 2018, 2019 all had 76 questions, whereas 2014 only had 26).
* Respondents believe that they would prefer not to talk about their mental health in their current employer as they believe that there would be negative consequences. But they would much less prefer talking about their `physical health` as the average is only `0.155`.
* Current employers that our respondents worked for had more than not formally talked about mental health through official channels. This is actually way better than what respondents were getting in their previous employers. Meaning current employers are much more likely to talk about mental health disorders formally than previous employers.
* People are more comfortable with talking about mental health with their `current employers`, rather than their `current coworkers`. Respondents also feel more comfortable (on average) to talk to `current supervisors` about mental health issues, compared to `previous supervisors`. This indicates a positive trend of people finding better employers over time.
* Very few people were willing to share mental health issues during a potential employers job interview. But much more willing to share about a physical issue.
* Distributions between whether people had or did not have any mental health disorders is not dependent on `age`, which means that `age` is not really a factor in whether people suffer from mental health disorders.
* `Tech organizations` have lower amounts of people reported to be `suffering from mental illness`, compared to their non-tech counterparts. Tech organizations are where people feel more comfortable discussing their mental woes with their supervisors, compared to their non-tech counterparts as well. 
* People with `mental health disorder histories` in their families seem to be less likely to talk about mental health issues during interviews by around `10%`.
* There is somewhat a direct positive correlation between people feeling comfortable talking with about their `physical health` with their `supervisors` and talking about mental health with their `supervisors` - the more willing you are to talk about one, the more likely you will talk about the other. The same trend can be seen for `mental v physical health discussions` in job interviews, as well.
