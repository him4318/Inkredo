## Background

Discovery (a team at Wikimedia) rely on event logging (EL) to track a variety of performance and usage metrics to help them make decisions. Specifically, Discovery is interested in:
* **click through rate:** the proportion of search sessions where the user clicked on one of the results displayed.
* **zero results rate:** the proportion of searches that yielded 0 results.

and other metrics outside the scope of this task. EL uses JavaScript to asynchronously send messages (events) to the servers when the user has performed specific actions. In this task, you will analyze a subset of their event logs.

## Task
* What is their daily overall clickthrough rate? How does it vary between the groups?
* Which result position do people tend to try first? How does it change day-to-day?
* What is their daily overall zero results rate? How does it vary between the groups?
* Let session length be approximately the time between the first event and the last event in a session. Choose a variable from the dataset and describe its relationship to session length. Visualize the relationship.
* Train and Test a simple Classifier to predict if a user is likely to click on one of the search result that appears. Transform the data accordingly. (Bonus points for writing a classifier from scratch) Choose appropriate metrics to measure the performance of your algorithm and visualize the predictions if possible.

## Data
| Column        |  Description  |
| ------------- |  ------------- |
| uuid  | Universally unique identifier (UUID) for backend event handling.  |
| timestamp  |The date and time (UTC) of the event, formatted as YYYYMMDDhhmmss.|
| session_id  |A unique ID identifying individual sessions.|
| group  |A label ("a" or "b").|
| action  |Identifies in which the event was created. See below.|
| checkin  |How many seconds the page has been open for.|
| page_id  |A unique identifier for correlating page visits and check-ins.|
| n_results  |Number of hits returned to the user. Only shown for searchResultPage events.|
| result_position  |The position of the visited page's link on the search engine results page (SERP).|
