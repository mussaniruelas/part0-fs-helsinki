# Name: Mussani Alejandro Manuel Ruelas Moran
## 0.6: Nueva nota en diagrama de aplicación de una sola pagina
Crea un diagrama que represente la situación en la que el usuario crea una nueva nota utilizando la versión de una sola página de la aplicación.



```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: Previously the notes page was already loaded.

    
    Note right of browser: Now we notice that the browser sends only a single request to the server.

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

    activate server
    
    Note right of browser: The POST request to the address new_note_spa contains the new note as JSON data <br> containing both the note content and the timestamp (date).

    server-->>browser: HTTP 201 "Created"
    deactivate server

    Note left of server: The server responds with status 201 Created. This time, <br> the server does not request a redirect <br> and the browser stays on the same page and does not send any more HTTP requests.

```