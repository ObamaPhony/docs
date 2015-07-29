* We start by asking the user for a list of **topic words**: nouns (or phrases
  which can be used as nouns) which will replace other nouns in the sentences we
  find.
* OPTIONAL: We then generate a special intro paragraph to make it sound more
  like the speaker we're using. Not sure if we want this or if it will be
  useful.
* For each topic word, we generate **one paragraph**.

Paragraphs
----------

  * To start a paragraph, we choose a random selection of all the **first
    sentences of paragraphs** in all of the speaker's speeches.
  * We replace a **random word** in each sentence with a random **topic word**.
  * The user selects one of the supplied sentences.
  * The rest of the paragraph is processed, with random nouns being replaced
    with the topic word (and possibly other topic words as well).
