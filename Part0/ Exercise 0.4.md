# 0.4: Exercise / Ejercicio 0.4

```mermaid
sequenceDiagram
    Title: 0.4: Exercise / Ejercicio 0.4

    participant Browser
    participant Server

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML document, Status 200 (OK)

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser: main.css, Status 200 (OK)

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Browser: main.js, Status 200 (OK)

    note over Browser: 
        Browser executes JavaScript, which will 
        request data with a GET request.
    end note

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Browser: data.json, Status 200 (OK)

    note over Browser:
        Browser starts executing the event handler 
        that populates the data into the ul in li's.
    end note

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/favicon.ico
    Server-->>Browser: favicon.ico, Status 200 (OK)

    note over Browser:
        User enters message.
    end note

    note over Browser:
        User clicks Save.
    end note

    Browser->>Server: POST Request to https://studies.cs.helsinki.fi/exampleapp/new_note

    note over Server:
        Server adds the post to an array of post-objects.
    end note

    Server-->>Browser: Response 302 (Redirect, new GET Request)

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML document, Status 304 (Not Modified)

    note over Browser:
        Browser reloads when receiving a new HTML file.
    end note

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser: main.css, Status 200 (OK)

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Browser: main.js, Status 304 (Not Modified)

    note over Browser:
        Browser executes JavaScript, which will 
        request data with a GET request.
    end note

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Browser: data.json including the new post, Status 200 (OK)

    Browser->>Server: GET Request to https://studies.cs.helsinki.fi/favicon.ico
    Server-->>Browser: favicon.ico, Status 200 (OK)



    end
```
