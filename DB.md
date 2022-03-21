# DB Tables
- Tasks (tasks)
- Task Types (task_types)
- Task Activities (task_activities)
- Task Activity Types (task_activity_types)
- Prospects (rep_prospects)
- Prospect Category (task_prospect_categories)
- Prospect Status (task_prospect_status)
- Sample Items (task_prospect_samples)
---
- Training Sharing Configurations (task_sharing_config) Task에 노출되는 Share Section 설정
- Training Sharing Analytics (task_share_analytics) - Share 추적
- Training Subject Types (task_training_types)
- Training Element Types (task_training_element_types)
- Training Subjects (task_training_subjects)
- Training Items (task_training_items)
- Training Items in a Subject (task_training_subject_items)
- Training Elements (task_training_elements)
- Training Elements in an Item (task_training_item_elements)
- Training Users' Subject (tasks_training_subject_users)
- Training Users' Training Items in Subject (tasks_training_subject_item_users)
---
# DB FKs (Foreign Keys)
|         **Table** | **Fields**         |        **Reference Table** | **Reference Field** | **Comment** |
|------------------:|--------------------|---------------------------:|---------------------|-------------|
| `rep_prospectors` | rep_id             |                     `reps` | id                  |             |
| `rep_prospectors` | category_id        | `task_prospect_categories` | id                  |             |
| `rep_prospectors` | prospect_status_id |     `task_prospect_status` | id                  |             |
---
| **Table** | **Fields**  | **Reference Table** | **Reference Field** | **Comment** |
|----------:|-------------|--------------------:|---------------------|-------------|
|   `tasks` | rep_id      |              `reps` | id                  |             |
|   `tasks` | rep_number  |              `reps` | number              |             |
|   `tasks` | type_id     |        `task_types` | id                  |             |
|   `tasks` | prospect_id |     `rep_prospects` | id                  |             |
---
|         **Table** | **Fields**       |   **Reference Table** | **Reference Field** | **Comment** |
|------------------:|------------------|----------------------:|---------------------|-------------|
| `task_activities` | activity_type_id | `task_activity_types` | id                  |             |
| `task_activities` | prospect_id      | `rep_prospects`       | id                  |             |
| `task_activities` | task_id          | `tasks`               | id                  |             |
---
| **Table**                | **Fields**           | **Reference Table**      | **Reference Field** | **Comment** |
|--------------------------|----------------------|--------------------------|---------------------|-------------|
| `task_training_subjects` | dependent_subject_id | `task_training_subjects` | id                  |             |
| `task_training_subjects` | organizer_id         |                   `reps` | id                  | Nullable    |
| `task_training_subjects` | organizer_number     |                   `reps` | number              | Nullable    |
---
| **Table**             | **Fields**       | **Reference Table**   | **Reference Field** | **Comment** |
|-----------------------|------------------|-----------------------|---------------------|-------------|
| `task_training_items` | training_type_id | `task_training_types` | id                  |             |
---
| **Table**                | **Fields**          | **Reference Table**           | **Reference Field** | **Comment** |
|--------------------------|---------------------|-------------------------------|---------------------|-------------|
| `task_training_elements` | element_type_id     | `task_training_element_types` | id                  |             |
---
| **Table**                     | **Fields**          | **Reference Table**      | **Reference Field** | **Comment** |
|-------------------------------|---------------------|--------------------------|---------------------|-------------|
| `task_training_subject_items` | training_subject_id | `task_training_subjects` | id                  |             |
| `task_training_subject_items` | training_type_id    |    `task_training_types` | id                  |             |
---
| **Table**                     | **Fields**          | **Reference Table**           | **Reference Field** | **Comment** |
|-------------------------------|---------------------|-------------------------------|---------------------|-------------|
| `task_training_item_elements` | training_subject_id | `task_training_subjects`      | id                  |             |
| `task_training_item_elements` | training_item_id    | `task_training_items`         | id                  |             |
| `task_training_item_elements` | element_type_id     | `task_training_element_types` | id                  |             |
---
| **Table**                      | **Fields**          | **Reference Table**      | **Reference Field** | **Comment** |
|--------------------------------|---------------------|--------------------------|---------------------|-------------|
| `tasks_training_subject_users` | rep_id              |                   `reps` | id                  |             |
| `tasks_training_subject_users` | rep_number          |                   `reps` | number              |             |
| `tasks_training_subject_users` | training_subject_id | `task_training_subjects` | id                  |             |

| **Table**                    | **Fields**                  | **Reference Table**              | **Reference Field** | **Comment** |
|------------------------------|-----------------------------|----------------------------------|---------------------|-------------|
| `tasks_training_items_users` | rep_id                      |                           `reps` | id                  |             |
| `tasks_training_items_users` | rep_number                  |                           `reps` | number              |             |
| `tasks_training_items_users` | training_subject_id         |         `task_training_subjects` | id                  |             |
| `tasks_training_items_users` | training_item_id            |            `task_training_items` | id                  |             |
| `tasks_training_items_users` | training_subject_item_id    |    `task_training_subject_items` | id                  |             |
