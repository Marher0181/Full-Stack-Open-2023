sequenceDiagram
    Title: 0.6: Exercise / Ejercicio 0.6

    participant browser
    participant server

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    server-->>browser: HTML

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: main.css

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server-->>browser: main.js

    note over browser: 
        Browser starts executing JavaScript code 
        that requests JSON data from the server.
    end note

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: 
        [
            { content: "whatever, just a simple content", date: "2020-11-30" },
            ...
        ]

    note over browser: 
        When the user types something in the bar, 
        for example, "Your inputting content," and presses "Save."
    end note

    browser->>server: HTTP POST {note: 'Your inputting content.'}

    note over server: 
        The server sends a response, a JSON indicating 
        "Note created."
    end note

    server-->>browser: new_note_spa

    note over browser: 
        Browser reloads the page.
    end note
