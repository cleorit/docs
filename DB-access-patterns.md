# NoSQL query access patterns

| Access pattern | Table/GSI/LSI | Key Condition | Example | Route |
|---|---|---|---|---|
| Get sentences from language | Language_Data | PK = language | PK = lang#english | GET /sentences/:lang_id |
| Get translation from sentence into DestLanguage | Language_Data | PK = SourceLanguage;Sentence, SK begins_with t!DestLanguage | PK = lang#english;sid#0001, SK begins_with t!lang#portuguese | GET /sentences/:sentence_id/target/:lang_id |
| Search for sentence | Language_Data/GSI1 | PK = sentence, SK = sentence | PK = sntc#Are you ok?, SK = sntc#Are you ok? |  |
| Get translations from user in a language to a language | Language_Data/GSI1 | PK = user;SourceLanguage, SK begins_with t!DestLanguage | PK = user#0001;lang#english, SK begins_with t!lang#portuguese | GET /users/:user_id/:lang_id/target/:language |
| Get cards that need to be reviewed | Review_Data | PK = user, SK <= today | PK = user#0001, SK <= 26/10/2021 | GET /schedule |
| Get user data | Language_Data | PK = user, SK = user | PK = user#0001, SK = user#0001 | GET /users/:user_id |
| Get user's vote for translation | Language_Data | PK = SourceLanguage;Sentence, SK = v!user;DestLanguage | PK = lang#english;sid#0001, SK = v!user#0001;lang#portuguese | GET /sentences/:sentence_id |
