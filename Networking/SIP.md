# SIP (Session Initiation Protocol)
- It's an application layer protocol used to establish, modify and terminate multimedia sessions (multimedia conferences, remote education, internet telephony, etc.) or calls.
- SIP transparently supports name mapping and redirection services, allowing the implementation of ISDN, IN and subscriber mobile services.
- SIP supports 5 facets of establishing and terminating multimedia communications:
    - User location: determination of the end system.
	    - Obtain information about a called subscriber's possible location.
	- User capabilities: determination of the media and media parameters.
	- User availability: determination of the willingness of the called party.
	- Call setup: "ringing", establishment of call parameters at both called and calling party.
	- Call control: establish, modify and terminate multimedia sessions or calls.

- A Redirect Server is a server that accepts a SIP request, maps the address into 0 or more new addresses and returns these addresses to the client.
- A Registrar is a server that accepts REGISTER requests. It's typically co-located with a proxy or redirect server and may offer location services.
- A User Agent is a logical entity that can initiate or receive SIP requests.

- There are two types of messages:
	- Request messages - invoking a particular operation, including INVITE, ACK, BYE, CANCEL, REGISTER, OPTION…
	- Response messages - responses to requests, including 1xx, 2xx, 3xx, 4xx, 5xx, 6xx and ACK.
	- Both types of messages contain SIP header fields and SIP message fields.

### SIP port: **5060**.

### **Request messages**
|Message	|Function|
|-|-|
INVITE|	Initiate a session request.
ACK|	The response message to the INVITE message.
BYE	|End session command.
CANCEL|	Cancel an unfinished request.
REGISTER|	Register
OPTIONS|	Query server's capabilities.
INFO|	Interactive contents when a call is being processed.
MESSAGE|	Short message.
SUBSCRIBE|	Subscribe to an event.
NOTIFY|	Send event notice.
### [**Response messages**](../Standards/HTMLresponse.md)