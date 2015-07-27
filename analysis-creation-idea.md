* Per sentence, generate:
  * A common/important phrase 'summing up' the sentence (string/phrase)
    * Drop articles etc. e.g. 'the', 'a'
    * Look especially for certain things such as 'Thank you'
  * The summed-up phrase of the previous sentence (string/phrase)
  * The position of the sentence in the full speech (float/percentage)
    * Out of 1
  * Anything else?
    * `word_length`: number of words in the sentence

* Output in JSON, each sentence in its own element:

```
{
    "data": [
        {
            "sentence": "Thank you, thank you, we all hate the republicans.",
            "summary": "republicans",
            "prev_summary": "thank you",
            OR
            "summary": [ "hate", "republicans" ]
            "prev_summary": [ "thank you", "thank you" ]
            "position": 0.7
        },
        {
            ...
        }
    ]
}
```

* Speech generation/interface:
  * 'Topic' word(s) are input to base the speech around. (TODO: just 1, or
    more?)
  * Wanted speech length is input
  * For each sentence:
    * The wanted sentence has some variables set:
    ```
    "wanted_summary": "americans"
    "wanted_prev_summary": "thank you"
    "wanted_position": 0.05
    ```
    * This sentence is compared to every other sentence in the database, and for
      each one a `"relevance"` variable is generated (float, 0 -> 1)
      * Also, for some special summaries/positions, there may be extra
        sentences/phrases generated, e.g. if `"wanted_summary": "thank you"`,
        then the sentence "Thank you" will *always* be generated with high
        relevance e.g. 0.95.
    * The X sentences with highest relevance are displayed as options for the
      next sentence, sorted by relevance (highest first)
    * Of those, the X most relevant sentences are highlighted.
    * Multiple sentences are generated/ripped by relevance (current speech
      position, previous summary, wanted summary)
      * e.g. the first sentence will often be the wanted summary

* Summary algorithm:
  * Remove common words:
    * articles: "the", "a"
    * "all"
    * pronouns (?)
