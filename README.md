RESTON
======

 Motivation
---------------

Everybody needs to communicate with somebody. Communication needs some standardization.
The standard needs to be easy, clear, helpful, and universal. In this instance, our communication means should remain independent of the medium we use to actually communicate, and yet it should be able to utilize it.

I can imagine that I use TCP, UDP, HTTP(S), Unix sockets, IPC, RPC, ZeroMQ, or any other means to communicate. These are all easy, and have their own field of utilization. However, each time you use any of them in an arbitrary communication, you need to invent your own protocol on top of them.

In the realm of ubiquitous web, REST rules. If you generalize it a little bit, and add the missing parts you must get something that resembles *RESTOM*.
RESTOM is clear, easy, useful for most use cases, and provides a standard way for any kind of communication.

General description
--------------------------

### Object Notion

First what is Object Notion. ON is based on JSON, and is a high level description of our capability to transport structured data.
On ON there is Number, String, List, Map, and No other bullshit.


### Sentence

A RESTON sentence is a 3-tuple of a resource identifier, a verb, and a pilot.
Resource identifier is a POSIX style path.
Verb is some word from a predefined set of words.
Pilot is an optional data that the verb might need, and is based on ON.

### Response

The response is a 2-tuple of a status code from the http set of status codes, and an optional blob.

### Transaction

The world of machines is transactional. So, any good and behaving RESTOMy machine has to support two special sentence BEGIN TRANSACTION, and END TRANSACTION. The response of end transaction sentence has to be 2xx-ish only when the result of all sentences from the associated begin transaction through on would be 2xx-ish.


Actual Implementation
------------------------------

The actual implementation doesn't actually matter. :-) We are all developers. What matters is the simplicity and ease of debugging. RESTON can be on top HTTP and actual REST. Or it can be implemented using ZeroMQ and BSON. It doesn't matter the actual syntax or semantics of numbers or encoding of strings in the specification. As the experience proved that we never get those things right, in the end. And rightfully the purpose of this specification also lies not on them.
