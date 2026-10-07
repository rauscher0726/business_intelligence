# Extra Instructions

Rules the LLM follows when it writes SQL for `listings`.

- `price` is the nightly price in U.S. dollars. When the user asks what something costs, use `price` and round money to whole dollars in the answer.

- `host_is_superhost` and `instant_bookable` are stored as the single-character
  text values 't' and 'f' (not SQL booleans). Always compare with quotes, e.g.
  `WHERE host_is_superhost = 't'`, never `WHERE host_is_superhost = TRUE`.

-- When the user types a city name, match it case-insensitively and allow for
  extra whitespace, e.g.
  `WHERE LOWER(TRIM(city)) = LOWER(TRIM('Austin'))`
  Do not assume the casing in the database matches what the user typed.



<!-- Add more rules below (Assignment 05 asks for at least three). Good candidates:
     `host_is_superhost` and `instant_bookable` are the text values 't' and 'f',
     not booleans; how to match a city name the user types; how to search `name`
     case-insensitively; and whether to ignore rows whose `review_scores_rating`
     is NULL when averaging ratings. -->
