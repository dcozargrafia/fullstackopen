```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a not and <br />clicks Save button

    Note right of browser: Browser executes event handler<br />preventing form submit

    NOte right of browser: Browser adds new note to notes list<br />and redraws notes

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: Content-type: application/json<br />{"content": "new note", "date": "2024-12-24"}
    activate server
    Note left of server: Server adds new note<br />to the notes array
    server-->>browser: Status (201) Created
    deactivate server

