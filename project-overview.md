If Obama Wrote a Speech About...
================================

Project name
------------

Project name: If Obama Wrote a Speech About...

As a program, we should refer to it as a 'speech generator', optional 'Obama'
prefix.


Group members
-------------

  * Ben Orchard
  * Patrick Geragersian
  * Dominic Rodriguez
  * Saleem Rashid


Description
-----------

### Tagline / Intro

Generate a speech about a topic in the style of Obama.


### Long

The project's aim is to generate a unique (though perhaps questionably original)
speech using a corpus of speeches by a specific speaker. We began with the idea
to use Barack Obama, but any speaker could be used, providing you have a large
enough collection of correctly-formatted speeches.

Generates a speech about chosen topic words using paragraphs from their previous
speeches.


Parts
-----

  * **Saleem:** Node.js server
  * **Dominic:** Go API
  * **Ben:** Python analysis program
  * **PG:** VB scraping program


Program flow
------------

  1. **Node.js server** starts up
  2. **Node** looks for a *speech cache*
       * If not present, **Node** calls the **scraping program** and saves the
         speeches into the *speech cache*
  3. **VB scraping program**, passes it to the **API**
  4. **API** sends speeches to the **analysis program**
  5. **API** stores returned analysed speeches
       * TODO: in memory/database/file?
  6. Ready for requests
  7. User inputs a number of *topic words* (maybe suggested 3?)
  8. User hits


Old flow
--------

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
