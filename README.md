
Files:

For each task, each coder gets a single JSONL. All written to the same database
afterward.

Fields:

- article ID
- article title
- text
- all three assigned coders in a list
- current assigned coder

DBs:

- `gsr_is_protest`: accept/reject protest label
- `gsr_mark_protest_verb`: highlighted protest verb

Commands

```
# make dataset for collecting protests
prodigy dataset gsr_is_protest "Collect accept/reject labels for whether a sentence contains a protest"
prodigy dataset gsr_mark_protest_verb "Highlight the verb phrase that makes it a protest"

# launch for a specific coder
prodigy mark gsr_is_protest protest_for_Youssef.jsonl --label PROTEST --exclude event_geolocation

# launch for highlight (for now, all three)
prodigy ner.manual gsr_is_protest en_core_web_sm protest_for_classification_Youssef.jsonl --label VERB,SOURCE,TARGET
```
