# Map/Reduce - Wordcount
Wordcount is the paradigmatic example of Map/Reduce, which counts the number of occurrences of each word in a document.
  - The mapper emits &ltword, 1&gt as the  &ltkey, value&gt
     * Get word
     * Emit &ltword, 1&gt
  - The reducer receives the shuffled &ltkey, value&gt pairs and aggregates the values for all the same keys
     * Get next &ltword&gt &ltvalue&gt
     * If &ltword&gt is same as previous word
        * add &ltvalue&gt to &ltcount&gt
     * else
        * emit &ltword&gt &ltcount&gt
        * set count to 0

Running wordcount_mapper.py and wordcount_reducer.py on testfile1 and testfile2 results in the wordcount_num0_output.txt file.