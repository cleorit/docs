# Basic Routes

```
GET /sentences/:lang_id => JSON with language data and first sentence ID

GET /sentences/:sentence_id => JSON with sentence data, and voted translation (if exists)
GET /sentences/:sentence_id/target/:lang_id => JSON with sentence and its translations
GET /sentences/:sentence_id/next => Returns a JSON w ith the next sentence according to the default order

POST /sentences/:sentence_id/translate, Creates a new sentence, according to JSON data
POST /sentences/:sentence_id/update, Creates a new sentence, according to JSON data
```

# User

``````
GET /users/:user_id => JSON with user data
GET /users/:user_id/:lang_id/target/:language => JSON with translated sentences in source language for target language
``````

# Voting:

```
PUT /sentences/:sentence_id/{up,down,neutral}
```
Stores a vote to the sentence.

# Scheduler:

```
GET /schedule => schedule with today's reviews
POST /shedule/:sentence_id/{again,good} => reschedules the sentence according to the user answer
```
