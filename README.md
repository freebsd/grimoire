# FreeBSD: Characterization of the Bugzilla Backlog

🤝 This analysis is the result of a partnership between Bitergia and the FreeBSD
Community, as an effort to make a characterization of the backlog from FreeBSD’s Bugzilla
instance.

⚙️ We produced a series of Dashboards to help with this characterization. Learn more
details in the [Characterization Dashboards](#characterization-dashboards) section.

📈 Here you will find the slide deck summarizing the results from the characterization.
Although the whole history has been analyzed, we agreed to focus on the open bugs from
the last two years and the last year, starting with the bugs from the Base System product.
This analysis can be extended to other periods and products by selecting the appropriate
options.

📁 **Index**

* [Slides: Characterization of the Bugzilla Backlog](#slides-characterization-of-the-bugzilla-backlog).
* [Characterization Dashboards](#characterization-dashboards).
* [How to import the dashboards from OpenSearch Dashboards](#how-to-import-the-dashboards-from-opensearch-dashboards).

## Slides: Characterization of the Bugzilla Backlog

Click [here](docs/FreeBSD-Characterization_of_the_Bugzilla_Backlog.pdf) to access the PDF
version of the slide deck.

## Characterization Dashboards

All these dashboards are available under the `dashboards` folder from this repository.
The instructions to import them into OpenSearch Dashboards are available in [this section](#How-to-import-the-dashboards-from-OpenSearch-Dashboards).

### Characterization 1 - Overview

This dashboard offers an overview of the Bugs submitted for all the Products in the
selected period, detailing the amount of activity coming from each Product.

![Overview](imgs/Characterization1-Overview.png)

### Characterization 2 -  Backlog Growth

This dashboard focuses on efficiency in closing bugs in the selected time frame. The
Evolution of the Backlog shows how the backlog has changed during the selected time frame,
while the BMI (Backlog Management Index) measures efficiency in closing issues. The
Bugzilla index does not contain the closing date of the Bugs, so the values are
approximated using the date of the last comment in "Closed" bugs.

![Backlog Growth](imgs/Characterization2-Backlog_Growth.png)

### Characterization 3 - Open Bugs: Attention times

This dashboard provides a breakdown of the open Bugs submitted during the selected period,
focusing on "Unattended" and "Abandoned" Bugs. A Bug will appear as "Unattended" when it
does not receive any comment from a user different from the author who created it. A bug
will appear as "Abandoned" when there were other comments, but the last comment was made
more than 3 months ago.

![Open Bugs - Attention Times](imgs/Characterization3-Open_Bugs_Attention_times.png)

### Characterization 4 - Open Bugs Needing Attention

Dashboard focused on the Open Bugs needing more attention, submitted during the selected
period. A Bug will appear as "Unattended" when it does not receive any comment from a user
different from the author who created it. A bug will appear as "Abandoned" when there are
other comments, but the last comment was made more than 3 months ago. By default, Bugs
with severity "Affects Only Me" are excluded.

![Open Bugs - Needing Attention](imgs/Characterization4-Open_Bugs_Needing_Attention.png)

### Characterization 5 -  Enhanced Bug List

This dashboard offers an enhanced version of the [bug list from Bugzilla](https://bugs.freebsd.org/bugzilla//buglist.cgi?bug_status=__open__&no_redirect=1&order=Importance&query_format=specific),
showing the list of Bugs submitted during the selected period. The results are limited to
2,000, in descending order by their creation date. The "Filters" widget on the left can be
used to narrow down the search. Another way to reduce the number of results is to select a
smaller time frame.

![Enhanced Bug List](imgs/Characterization5-Enhanced_Bug_List.png)


## How to import the dashboards from OpenSearch Dashboards

To import the Dashboards provided by Bitergia (including the related visualizations and
the index pattern), go to the “Dashboards Management” section, click on “Saved Objects”
and then “Import.” Then, select the `.ndjson` files under the `dashboards` directory and
import them. We recommend to choose the option "Check for existing objects" and then
select "Request action on conflict".

You can import each dashboard individually, or import all the Characterization
Dashboards at once by selecting the file `all-characterization-dashboards.ndjson`.

Now, the dashboards should be available under the “Dashboards” section.

![How to import dashboards](imgs/import-dashboards.png)
