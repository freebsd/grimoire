# Bugzilla

This index contains one document per Bugzilla ticket.

The documents in this index are about the bugs reported in a Bugzilla instance. BAP can
extract information about the reporters, assignees, and resolvers of these issues.
It can also analyze the status, the number of changes, the number of comments, and other
metadata associated with each bug, such as the Product and Component on which the bug
was reported to.

## Data schema

The index names are in the format `bugzilla` or `bugzilla_enriched`.

All the field types are aggregatable except the `string` field type
(`description_analyzed` and `main_description_analyzed`).


| Name                                       | Type    | Description                                                                                                                           |
|--------------------------------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| assigned                                   | keyword | Assignee name, coming from Bugzilla.                                                                                                  |
| assigned_to_bot                            | boolean | True if the given assignee is identified as a bot.                                                                                    |
| assigned_to_domain                         | keyword | Domain associated to the assignee in SortingHat profile.                                                                              |
| assigned_to_gender (`disabled`)            | keyword | Assignee gender, based on their name.                                                                                                 |
| assigned_to_gender_acc (`disabled`)        | keyword | Assignee gender accuracy.                                                                                                             |
| assigned_to_id                             | keyword | Assignee Id from SortingHat.                                                                                                          |
| assigned_to_multi_org_names                | keyword | List of the assignee organizations from SortingHat profile.                                                                           |
| assigned_to_name                           | keyword | Assignee name.                                                                                                                        |
| assigned_to_org_name                       | keyword | Assignee organization name.                                                                                                           |
| assigned_to_user_name                      | keyword | Assignee user name from SortingHat.                                                                                                   |
| assigned_to_uuid                           | keyword | Assignee's UUID from SortingHat profile.                                                                                              |
| assigned_to_detail_bot                     | boolean | True if the given assignee is identified as a bot.                                                                                    |
| assigned_to_detail_domain                  | keyword | Domain associated to the assignee in SortingHat profile.                                                                              |
| assigned_to_detail_gender (`disabled`)     | keyword | Assignee gender, based on their name.                                                                                                 |
| assigned_to_detail_gender_acc (`disabled`) | keyword | Assignee gender accuracy.                                                                                                             |
| assigned_to_detail_id                      | keyword | Assignee Id from SortingHat.                                                                                                          |
| assigned_to_detail_multi_org_names         | keyword | List of the assignee organizations from SortingHat profile.                                                                           |
| assigned_to_detail_name                    | keyword | Assignee name.                                                                                                                        |
| assigned_to_detail_org_name                | keyword | Assignee organization name.                                                                                                           |
| assigned_to_detail_user_name               | keyword | Assignee user name from SortingHat.                                                                                                   |
| assigned_to_detail_uuid                    | keyword | Assignee's UUID from SortingHat profile.                                                                                              |
| author_bot                                 | boolean | True/False if the author is a bot or not.                                                                                             |
| author_domain                              | keyword | Author's domain name from SortingHat profile.                                                                                         |
| author_gender (`disabled`)                 | keyword | Author gender, based on their name.                                                                                                   |
| author_gender_acc (`disabled`)             | keyword | Author gender accuracy.                                                                                                               |
| author_id                                  | keyword | Author's ID from SortingHat profile.                                                                                                  |
| author_name                                | keyword | Author's name.                                                                                                                        |
| author_org_name                            | keyword | Author's organization name from SortingHat profile.                                                                                   |
| author_multi_org_names                     | keyword | List of the author organizations from SortingHat profile.                                                                             |
| author_user_name                           | keyword | Author's username from SortingHat profile.                                                                                            |
| author_uuid                                | keyword | Author's UUID from SortingHat profile.                                                                                                |
| bug_id                                     | keyword | Id of the bug in Bugzilla.                                                                                                            |
| changeddate_date                           | date    | Datetime when the bug was last changed.                                                                                               |
| changes                                    | long    | Number of changes in the bug.                                                                                                         |
| comments                                   | long    | Number of comments in the bug.                                                                                                        |
| component                                  | keyword | The component on which the bug was reported.                                                                                          |
| creation_date                              | date    | Datetime when the bug was created.                                                                                                    |
| creation_ts                                | date    | Timestamp when the bug was created.                                                                                                   |
| creator                                    | keyword | Creator name, from Bugzilla.                                                                                                          |
| creator_detail_bot                         | boolean | True if the given Creator is identified as a bot.                                                                                     |
| creator_detail_domain                      | keyword | Domain associated to the Creator in SortingHat profile.                                                                               |
| creator_detail_gender (`disabled`)         | keyword | Creator gender, based on their name.                                                                                                  |
| creator_detail_gender_acc (`disabled`)     | keyword | Creator gender accuracy.                                                                                                              |
| creator_detail_id                          | keyword | Creator Id from SortingHat.                                                                                                           |
| creator_detail_multi_org_names             | keyword | List of the Creator organizations from SortingHat profile.                                                                            |
| creator_detail_name                        | keyword | Creator name.                                                                                                                         |
| creator_detail_org_name                    | keyword | Creator organization name.                                                                                                            |
| creator_detail_user_name                   | keyword | Creator user name from SortingHat.                                                                                                    |
| creator_detail_uuid                        | keyword | Creator's UUID from SortingHat profile.                                                                                               |
| delta_ts                                   | date    | The timestamp of the last update.                                                                                                     |
| description                                | keyword | Long description of the bug.                                                                                                          |
| description_analyzed                       | string  | FALSE                                                                                                                                 | Long description of the bug (analyzed).                                                                                              |
| grimoire_creation_date                     | date    | The creation date of the bug.                                                                                                         |
| id                                         | long    | The bug ID.                                                                                                                           |
| is_bugzilla_bug                            | long    | 1 if the item type is a bug.                                                                                                          |
| is_bugzillarest_bugrest                    | long    | 1 if the bug comes from the Bugzillarest backend.                                                                                     |
| is_open                                    | boolean | True if the status of the bug is open.                                                                                                |
| keywords                                   | keyword | Set of keywords added to the bug.                                                                                                     |
| labels                                     | list    | Custom repository labels defined by the user.                                                                                         |
| last_comment_date                          | date    | Datetime when the last comment was posted to the bug"                                                                                 |
| main_description                           | keyword | Short description of the bug / title.                                                                                                 |
| main_description_analyzed                  | string  | FALSE                                                                                                                                 | Short description of the bug / title (analyzed).                                                                                     |
| metadata__enriched_on                      | date    | Date when the item was enriched.                                                                                                      |
| metadata__gelk_backend_name                | keyword | Name of the backend used to enrich information.                                                                                       |
| metadata__gelk_version                     | keyword | Version of the backend used to enrich information.                                                                                    |
| metadata__timestamp                        | date    | Date when the item was stored in RAW index.                                                                                           |
| metadata__updated_on                       | date    | Date when the item was updated in its original data source.                                                                           |
| op_sys                                     | keyword | The operating system on which the bug was observed.                                                                                   |
| origin                                     | keyword | Original URL of the instance where the bug was retrieved from.                                                                        |
| painless_last_comment_delay                | string  | Time in days since the last comment was posted in the bug until the current time.                                                     |                                                                                                                                         |
| painless_time_to_now                       | float   | Contains the value of `timeopen_days` if the status is different from 'Closed' and the value of `resolution_days` otherwise.          |
| platform                                   | keyword | The platform on which the bug was reported.                                                                                           |
| priority                                   | keyword | The priority of the bug (P1 = most urgent, P5 = least urgent).                                                                        |
| product                                    | keyword | The product on which the bug was reported.                                                                                            |
| project                                    | keyword | Project (metadata).                                                                                                                   |
| project_1                                  | keyword | Project (metadata, if more than one level is allowed in project hierarchy).                                                           |
| qa_contact_bot                             | boolean | True if the given QA Contact is identified as a bot.                                                                                  |
| qa_contact_detail_bot                      | boolean | True if the given QA Contact is identified as a bot.                                                                                  |
| qa_contact_detail_domain                   | keyword | Domain associated to the QA Contact in SortingHat profile.                                                                            |
| qa_contact_detail_gender (`disabled`)      | keyword | QA Contact gender, based on their name.                                                                                               |
| qa_contact_detail_gender_acc (`disabled`)  | keyword | QA Contact gender accuracy.                                                                                                           |
| qa_contact_detail_id                       | keyword | QA Contact Id from SortingHat.                                                                                                        |
| qa_contact_detail_multi_org_names          | keyword | List of the QA Contact organizations from SortingHat profile.                                                                         |
| qa_contact_detail_name                     | keyword | QA Contact name.                                                                                                                      |
| qa_contact_detail_org_name                 | keyword | QA Contact organization name.                                                                                                         |
| qa_contact_detail_user_name                | keyword | QA Contact user name from SortingHat.                                                                                                 |
| qa_contact_detail_uuid                     | keyword | Creator's UUID from SortingHat profile.                                                                                               |
| qa_contact_domain                          | keyword | Domain associated to the QA Contact in SortingHat profile.                                                                            |
| qa_contact_gender (`disabled`)             | keyword | QA Contact gender, based on their name.                                                                                               |
| qa_contact_gender_acc (`disabled`)         | keyword | QA Contact gender accuracy.                                                                                                           |
| qa_contact_id                              | keyword | QA Contact Id from SortingHat.                                                                                                        |
| qa_contact_multi_org_names                 | keyword | List of the QA Contact organizations from SortingHat profile.                                                                         |
| qa_contact_name                            | keyword | QA Contact name.                                                                                                                      |
| qa_contact_org_name                        | keyword | QA Contact organization name.                                                                                                         |
| qa_contact_user_name                       | keyword | QA Contact user name from SortingHat.                                                                                                 |
| qa_contact_uuid                            | keyword | Creator's UUID from SortingHat profile.                                                                                               |
| reporter_bot                               | boolean | True if the given Reporter is identified as a bot.                                                                                    |
| reporter_domain                            | keyword | Domain associated to the Reporter in SortingHat profile.                                                                              |
| reporter_gender (`disabled`)               | keyword | Reporter gender, based on their name.                                                                                                 |
| reporter_gender_acc (`disabled`)           | keyword | Reporter gender accuracy.                                                                                                             |
| reporter_id                                | keyword | Reporter Id from SortingHat.                                                                                                          |
| reporter_multi_org_names                   | keyword | List of the Reporter organizations from SortingHat profile.                                                                           |
| reporter_name                              | keyword | Reporter name.                                                                                                                        |
| reporter_org_name                          | keyword | Reporter organization name.                                                                                                           |
| reporter_user_name                         | keyword | Reporter user name from SortingHat.                                                                                                   |
| reporter_uuid                              | keyword | Creator's UUID from SortingHat profile.                                                                                               |
| repository_labels                          | keyword | Custom repository labels defined by the user.                                                                                         |
| resolution                                 | keyword | The bug's resolution.                                                                                                                 |
| resolution_days                            | float   | Time in days between the bug's creation date and the date of the last change.                                                         |
| severity                                   | keyword | The bug's severity.                                                                                                                   |
| status                                     | keyword | The bug's status.                                                                                                                     |
| tag                                        | keyword | Original URL of the instance where the bug was retrieved from.                                                                        |
| timeopen_days                              | float   | Time in days since the creation of the bug until the current date.                                                                    |
| time_to_first_attention                    | float   | Time in days since the creation of the bug until the date of the first comment made in the bug by any user different from the author. |
| url                                        | keyword | The bug's URL.                                                                                                                        |
| uuid                                       | keyword | Perceval UUID.                                                                                                                        |
| whiteboard                                 | keyword | The bug's whiteboard field.                                                                                                           |
