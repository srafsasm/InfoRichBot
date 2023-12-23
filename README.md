# InfoRichBot

This is a repository for a research Chatbot is Not All You Need: Information-rich Prompting for More Realistic Responses. 

On this repository, we release our benchmark dataset and evaluation samples. 

Each files' structures look like below:

```markdown
inforich_benchmark.pickle
{
    movie_title001:
    {
        'character_info':
        {
            char1: {char1_attributes...},
            char2: {char2_attributes...},
            ...
        },
        'conversations':
        {
            conversation1:
            {
                'characters': [appearing_char1, appearing_char2, ...]
                'utterances': [{appearing_char1: utterance1}, {appearing_char2: utterance2}, ...]
                'background': background...
                'full_background': full_background...
                'character_state':
                {
                    appearing_char1: {"Vision": "...",
                                      "Smell": "...",
                                      "Hearing": "...",
                                      "Taste": "...",
                                      "Touch": "...",
                                      "Emotion": "...",
                                      "Memory": "...",
                                      "InterlocutorKnowledge": "..."},
                    appearing_char2: ...,
                    ...
                }
            }
            conversation2: ...,
            ...
        }
    },
    movie_title002,
    ...
}
```
```Mardown
* gen_raw: generation only given the background, previous dialogues, and character attributes.
* gen_senses: gen_raw + sense information
* gen_emotion: gen_raw + emotion information
* gen_memory: gen_raw + memory information
* gen_inter: gen_raw + interlocutor knowledge information
* gen_full: generation using all the components

[
    {
        "background": ...
        "ground_truth": ...
        "prediction": ...
    },
    ...
]
```

