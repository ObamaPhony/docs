Project overview
================

Description
-----------

### 1 sentence

Generates a speech about chosen words in the style of a chosen speaker using
paragraphs from their previous speeches.


### Long

The user picks a number of topic words


Parts
-----

  * **Saleem:** Node server
  * **Dominic:** Go API
  * **Ben:** Python analysis program
  * **PG:** VB scraping program


Program flow
------------

  1. Gather **speech collections** for speaker(s)
  2. Send to **API**
  3. **API** sends each **speaker** separately to the **sentence analyser**
     which returns information about each sentence in each speech
  4. Information is stored for each speaker
       * Could cache this if we end up restarting the server a *lot* -- however
         it's meant to be a 'long-life' process
  5. API is prepared for requests
  6. User enters information
       1. User selects a speaker
       2. User selects speech length
       3. User enters a **noun** (TODO: multiple?) (TODO: could show example
          nouns from Google Trends)
  7. For each sentence, API sends to the **relevance calculator**:
       * the full **speaker**
       * the current **position** (between 0 and 1)
       * the word to use (for that paragraph)
       * the previous summary
  8.

  1. 


Parts
-----

### Speech database

####


#### Downloading
#### Sorting
### Analysis

phrase = word/phrase/sentence




#### Common phrase counts
#### Common phrase placements
#### Phrase position in speech
#### Help!?!?!?!?
### Sentence generation
#### Random seed
#### Using analysis metrics
#### Who knows?!!
### Interface
#### API
