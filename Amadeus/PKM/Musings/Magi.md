---
Last edited time: "November 7, 2023 12:48 PM"
Status: "Unprocessed"
Created time: "November 6, 2023 9:25 PM"
---

# Magi

## Roadmap

- Magi CLI decoupled from Magi Server
- Simple chat like UX.
    - Chats should be stored in the local machine.
    - Example:
        
        ```tsx
        // $ magi chat <chatId>
        // [System] Chat model ready!
        // [System] Initializing chat interface
        // [System] Chat interface ready!
        // [System] Type anything to start...
        // [Magi] Hello there, how can I assist you today?
        // Hey magi, nice to meet you.
        // [Magi] OH thank you!, how can I assist you today?
        ```
        
- Notion integration:
    - We need to able to save chats into notion.
    - User should be able to set the notion api key.
    
    ```tsx
    # A
    ~~$ magi chat <chatId>
    [Magi] Hello there, how can I assist you today?
    >Save this chat to notion
    
    Option A Review:
    - Needs NLP tp understand things.
    - I don't have a way of passing specific parameters.
    When adding other features using NLP it becomes quite complex.
    - What about using GPT-4 json mode?
    
    # B
    $ magi chat <chatId>
    [Magi] Hello there, how can I assist you today?
    > /save-to-notion~~
    
    ~~Option B Review:
    - Easy to scale.
    - I would require knowledge in all the commands available.~~
    
    # C
    [Magi] Hello there, how can I assist you today?
    [ ] Send Message
    [ ] Upload File
    [ ] Save Chat to Notion
    
    Opcion C Review:
    - Easy to scale.
    - No cons of the option B.
    
    -----------------------------------------------------------------------
    
    Magi is currently tied to a "chat"... Let's rework that for agents.
    
    $ magi start
    Choose the core to use
    [ ] Second Brain
    [ ] Me as a Developer
    [ ] Me as a ...
    
    ## Me as a Person
    What do you need todo? (Me as a person) (Notion integration)
    [ ] Journal
    [ ] Reminder
    [ ] Expense
    [ ] Income
    [ ] USD Transference
    [ ] Chat -> Uses all second brain information to chat with me.
    
    ## Me as a developer
    
    	[ ] Send Message
    	[ ] Upload File
    	[ ] Save Chat to Notion
    ```
    
- Native OpenAI TTS
- ElevenLabs TTS
- Upload file support (via pathname)
-