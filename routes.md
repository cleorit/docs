# Basic Routes
```
GET /sentences/:sentence_id => JSON with sentence data
GET /sentences/:sentence_id/target/:lang_id => JSON json, with sentence and its translations
GET /sentences/:sentence_id/next => Returns a JSON w ith the next sentence according to the default order

POST /sentences/:sentence_id/translate, Creates a new sentence, according to JSON data
POST /sentences/:sentence_id/update, Creates a new sentence, according to JSON data
```
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
