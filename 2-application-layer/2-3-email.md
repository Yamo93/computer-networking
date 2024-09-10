# Email
## Email Delays

> **3 RTTs** are required from client contacting an email server via TCP to when the client can begin sending the email message after initial TCP and SMTP handshaking.

### HTTP Characteristics
* Uses a blank line (CRLF) to indicate end of request header.
* Operates mostly as a "client pull" protocol.
* Uses server port 80.

### SMTP Characteristics
* Uses CRLF.CRLF to indicate end of message.
* Operates mostly as a "client push" protocol.
* Uses server port 25.

### Both HTTP and SMTP Characteristics
* Is able to use a persistent TCP connection to transfer multiple objects.
* Has ASCII command/response interaction, status codes.

### Email Protocols
* SMTP pushes email from a mail client to a mail server.
* IMAP pulls email to a mail client from a mail server.
* Neither SMTP nor IMAP pulls mail from one mail server to another mail server.