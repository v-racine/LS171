<h1> How does the Internet Work? A Socratic Dialogue <h1>

SETUP => Ted (played by a young Keanu Reeves) is a LS student who, on a fortuitous day, discovers a phone booth-shaped time machine that allows him to time travel. He's immediately thrilled about the possibility of visiting different eras and speaking with historical figures. Maybe he'll try to meet up with Billy the Kid, Sigmund Freud, Ludwig van Beethoven, Joan of Arc, Genghis Khan or Abraham Lincoln! 

But before he sets out on all of these excellent adventures with his best mates, he knows he ought to study for the LS 171 assessment. Immediately, he starts to wonder how he can leverage his new discovery to help him prepare for the test. 

His first thought is to go back to the 90s and sit in on a meeting of the World Wide Web Consortium (W3C) or the HTTP Working Group (HTTP-WG). Or, maybe, he could go back a few years before that and visit Tim Berners-Lee and his team at CERN when they were first developing the ideas of the World Wide Web, URLs, and HTTP. "Should he go even further back?" he thinks to himself, "and have a chat with Vint Cerf and Bob Kahn about the development of the Transmission Control Protocol (TCP) and the Internet Protocol (IP)?"

Although it would be really cool to talk to all of these people as they were developing the components of the revolutionary technology we now refer to as the internet, they might not be the most helpful option available to him right now. (Also, they're all still alive so he can always send them a quick email later.) 

Then, Ted remembers the suggestion to write a blog post to answer the question "How does the internet work?" in the last lesson of LS 170. That makes sense! The best way to learn something is to clearly explain these concepts to someone else in your own words. 

Who would be the best person to have a conversation with about the Internet? They would have to be a smart and curious interlocutor, but not necessarily someone who's already an expert on the Internet. Actually, it'd be better if that person was NOT an expert on the Internet, so they could push Ted to explain all the concepts as clearly as possible. Someone who would ask questions like: "What do you mean by that?" and "Why is that the case, rather than something else?", or "How does this relate to the previous concept?" Someone as incessant and annoying as a gadfly...

It suddenly dawns on him. Ted will travel back to ancient Athens and have a conversation with Socrates about the Internet! Off he goes in his time machine. 

As he steps foot in a public square in ancient Athens, Ted spots Socrates right away. The old man is sitting on a rock and drawing squares and triangles in the sand as he scratches his beard with a look of puzzlement on his face. 

TED: What's up, Socrates? 

SOCRATES: Hey, young man! Do I know you? You're not a descendent of a wealthy Athenian, are you? 

TED: Not sure, I haven't checked that far back in my family tree... My name's Ted Theodore Logan and I'm from the future. Anyway, I'm trying to get clear about some pretty complex abstract concepts. Wanna chat?

SOCRATES: [Socrates's eyes light up.] Are you thinking about Truth?

TED: Not exactly... 

SOCRATES: Does it have anything to do with Justice?

TED: Not really. It's about technology, so it isn't inherently just or unjust. It's malleable and can support both just and unjust patterns of behaviour and institutional arrangements. Of course, that's assuming that we all agree about what counts as just...

SOCRATES: Ok, nevermind. [Socrates waves his hand dismissively.] I already had that conversation with the son of Ariston. Do you know him? 

TED: Nope. Sorry. 

SOCRATES: Ok, tell more about this concept. Does it have to do with Beauty?

TED: Well, when you think about it, it is kind of a beautiful complex system. It's called the Internet. It's defined as a network of networks that facilitates communication and information sharing. 

Socrates: ...sounds like when I get the sons of wealthy Athenians to question their beliefs and they go talk to their elders and their elders talk to each other, and then everyone gets mad at me for some reason... [Socrates makes a sad face then snaps out of it quickly]. Tell me more about this thing. 

TED: Ok, well, I think the best way to think about it is in terms of different layers of abstraction that are built upon a concrete, physical infrastructure. 

SOCRATES: Sounds like my pupil's obsession. He's always talking about these ideal forms...

TED: The layers provide a great model with which to think about how two devices can communicate over a vast network of networks. I'll explain all of this by walking you through the *request-response cycle*. Do you have any questions so far? 

SOCRATES: Nope, I'm good. 

TED: [Ted looks a little surprised.] Alright, then let's continue. So, in our model, we'll name the two devices that are communicating. I'll refer to one as the Client and the other as the Server. 

SOCRATES: Got it.

TED: OK, so the whole thing starts with a person typing a *URL* (Uniform Resource Locator) in a *browser* into the first device we called the Client. For example, someone in my era might want to learn more about you, Socrates. So, they might enter `https://plato.stanford.edu/`. 

SOCRATES: Ooh! Am I famous in your time? 

TED: Yeah, kinda. So, when that happens, the Client sends a request to the Server using a set of rules called *HTTP* (Hypertext Transfer Protocol). The Client expects the Server to send a response. And, when _that_ happens, the person who typed in the initial URL can view the information on a screen on their device. The whole process takes fractions of a second to complete, but there's _so_ much going on underneath all of this exchange.

SOCRATES: Sounds like magic to me! 

TED: It _feels_ like magic too! But really smart people figured out the whole process by developing protocols and adding security measures over several decades so that anybody can type in a request in a Client/browser and access the resources on the World Wide Web (a service that can be accessed via the internet). And, by the way, the Server can be located anywhere in the entire world (which is much larger than what you think it is... but we can talk about that some other time). So, let's dive deeper into this process.

SOCRATES: I'm very intrigued. Tell me more!

TED: Ok, so I mentioned that the Server, to whom we're sending our request can be located anywhere in the world, so the request can have quite a journey ahead of it. But, to keep things simple, let's start by explaining the process at the highest level of abstraction. This is referred to as *the Application Layer*. And, it's where the HTTP sets the rules. 

SOCRATES: Application layer is at the top. Got it. 

TED: So, I mentioned HTTP before. It's the protocol that is employed so that the Client and Server can understand the messages they're exchanging. When someone types in a URL, the Client (our browser, in this case) sends a `GET` request, which is a message asking to fetch or retrieve a resource from the Web.

SOCRATES: Okay, that makes sense. But, why did you make air quotes when you said `GET`?

TED: Well, because that term signifies the *HTTP request method*. It tells the Server what _kind_ of request you're making. The other required parts of an *HTTP request line* include the *path* and the *HTTP version*. Can I borrow that stick for a second? 

SOCRATES: Sure, here you go.

TED: Thanks! So, here's what it would look like: [Ted draws out the request line and the request header in the sand.]

```js
GET / HTTP/1.1
host: plato.stanford.edu 

(optional body) // not common with `GET` requests, but `POST` requests typically have a body 
```
TED: So, the request method here is `GET`. It's not the only option[footnote1], but it's the most common one when we're sending a request to retrieve information. The next part on that first line is the path. Here, the `/` just signifies the homepage of the host. The next component is the HTTP version, which in my example is `HTTP/1.1`. On the second line, we have the required "host" header that follows a `name: value` style syntax, which is _always_ followed by a blank line. The blank line separates the *HTTP request header* and *the HTTP request body*. 

SOCRATES: I think I'm following... but, how did you get all of that from typing in `https://plato.stanford.edu/`? What's the connection there?  

TED: Great question! The URL is loaded with information. The `https://` part is called the *scheme* and indicates which version of the HTTP protocol is in use. `plato.stanford.edu` is the *host* of course, and everything that comes after is the *path*; for example, `https://plato.stanford.edu/entries/socrates/`.[footnote2]

SOCRATES: Got it. So, you mentioned the URL is some kind of locator, right? So, it's like an address?  

TED: Well, yeah. But, the actual address of a resource on the web will be a series of numbers referred to as the *IP address* [footnote3], and something like `plato.standford.edu` is a *domain name*.

SOCRATES: Ok, slow down, buddy. What's the relationship between those two things?

TED: Before my time, someone had the brilliant idea that it'd be better if people could just request a resource by typing in a name instead of a series of numbers. It's just _so_ much easier to remember a name, dude! 

SOCRATES: Yeah, for the average plebian. [Socrates snickers.] But I guess you've got a point. 

TED: I don't know what that means, dude. Anyway, so they came up with the *Domain Name System*. For example, `plato.stanford.edu` is an alias for its actual address, `171.67.193.20`. As I mentioned before, that's the IP address and the entire remote address can also include a port. Depending on the actual protocol in use, often the port for the request is left implicit. For example, we've been using `HTTPS`, so that'll be port `443` but `HTTP` will use port `80`, as the respective default port. I'll tell you more about `HTTPS` a little later, if you're interested to learn about security. 

SOCRATES: Sure! But, first, let me get clear about this whole requesting process. How does the Domain Name System work exactly?

TED: Well, the DNS is a huge distributed database that keeps track of which domain name matches which IP address, and converts the name into its corresponding IP address during a request. And, on a side note, most modern browsers will cache the IP address of a domain name from previous browser sessions, so they don't have to look it up again every time a request is made[footnote4]. 

SOCRATES: That makes sense. 

TED: Okay, great. We're going to shift gears and go to the next level of abstraction. It's called *the Transport Layer*. Are you ready?

SOCRATES: I'm dying of excitement! 

TED: Okay, so we have the IP address and the port. Those two things together are referred to as a *socket*, and it indicates where our request is headed. But the Client has to first establish a connection with that endpoint. That's where the *Transport Layer Protocol (TCP)* comes in. 

SOCRATES: So, the TCP provides the rules to establish that initial connection between the two parties? 

TED: Exactly! And, the way that happens is the *TCP three-way handshake*. First, the Client/browser sends a `SYN` message, that's sort of like it saying: "Hey Server, are you there?". Then, the Server responds by sending a `SYN/ACK` message, or "Yeah, I'm listening. What's up?". Finally, the Client/browser sends a last message `ACK`, or "Cool! Here's what I want.". After that third message, the Client/browser can start sending data to the Server. 

SOCRATES: That makes sense. But, why do they have to do this initial back-and-forth before sending any messages of substance? Is it for security purposes?

TED: Great question! I knew I made the right choice coming to ancient Athens to talk to you about the Internet. No, it's not about security, actually. There's a different handshake for that, and we'll get to it a little later. It has more to do with reliability.
The TCP handshake is meant to ensure there is an established, /reliable/, connection between the two parties. The TCP ensures that: 
(1) the data is not altered during the transit; 
(2) the data isn't lost during the transit, and if it is, then the data (in the form of *packets* [footnote5]) is resent; 
(3) the data packets are numbered and sent and received in lexical order; and 
(4) the flow of data is controlled by establishing a "window" of how much data can be transmitted at the same time.
TCP also enables *multiplexing*, which is just the ability to send multiple signals over a single established connection between two devices (identified by their IP addresses). That's important when the Server/host is sending back a lot of data in different formats, such as CSS files, JS files, images, videos, and more, in addition to the HTML file.

SOCRATES: Ok, so TCP sets up the connection to transmit the data and it's important to do that for *reliability*, *the ordering of data packets*, *flow control*, and *multiplexing*. Is that right? 

TED: Yeah, that's a good summary. 

SOCRATES: Is that why it does the whole "back-and-forth" thing initially? 

TED: Yes. But it does come at a cost. 

SOCRATES: What do you mean?

TED: Well, there is always a trade-off when talking about the protocols at the different layers of abstraction. At the transport layer, the initial round-trip of the TCP handshake trades performance for reliability. We talk about this cost in terms of *latency*, which, in broad terms, is a measure of delay. In our current context, this is often referred to as the Round-trip Time (RTT), which measures the time for the signal to be sent plus the time for an acknowledgment or response to be received [footnote6].

SOCRATES: Got it. 

TED: Ok, let's move on to the next layer, *the Internet/Network Layer*. 

SOCRATES: Wait a sec, I'm a little confused. How are all the different layers connected to each other? 

TED: Oh, great question! Now's a good time to talk about *encapsulation*. In our mental model, the upper layer contains the main message being sent across the channel and it is encapsulated into the next, lower level, where it is referred to as that level's *data payload*. So, let's think about the layers we've already discussed. The message in the HTTP request is encapsulated into the data payload of the *TCP segment* in the Transport Layer. In turn, the TCP segment is encapsulated into the data payload of the *IP packet* in the Network Layer. And, finally, the IP packet is encapsulated in the data payload of the *Ethernet frame* in the Data Link/Link Layer. At each level, these units are referred to as the *Protocol Data Units (PDUs)*, which contain the encapsulated data to be transported (i.e. the data payload), and some meta-data that is attached in the form of header and trailer fields. We'll talk about the other layers and their PDUs in a minute, but first, let's go back to the Network Layer.

SOCRATES: I think I have a better mental image of the layers in my head now. Thanks! 

TED: At the Transport Layer, the TCP Segment has a header that stores the port number of the message source and destination. As I just mentioned, the segment is encapsulated into the data payload at the Internet/Network layer, where the *Internet Protocol (IP)* is at play. The IP packet concerns itself with the IP addresses of the message source and destination. 

SOCRATES: Ok, so at this level, we're talking about the actual path between the source and the destination? 

TED: Right! The Server/host could be anywhere in the world. The IP figures out the path for the request-response cycle over the network.
Finally, below the Network Layer, we get to *the Data Link/Link Layer*. Here, the IP packet is encapsulated as the data payload inside a *frame*. The frame has several components, including some logical bits with a header that stores the *MAC addresses* of the source (here, we are talking about the address linked to the specific device that created the frame) and the destination (the address linked to the specific device to which the initial data is intended to reach). That's a key component of this layer. 

SOCRATES: The MAC addresses?

TED: Yeah, MAC addresses provide identification numbers that are permanently tied to specific devices. In that sense, we can think of them as physical rather than logical. And, their identification numbers are *flat* rather than hierarchical. 

SOCRATES: What does that mean? 

TED: Well, unlike IP addresses we discussed earlier, a MAC address is a single sequence of values and we can't parse them into sub-divisions. 

SOCRATES: Gotcha! 

TED: Ok, finally, the logical bits in the Data Link/Link Layer are converted to binary signals to be transmitted at *the Physical Layer*. At that very first (foundational) layer of our layer-cake model, the data travels through an Ethernet cable, fiber optic cable, or radio waves until it reaches its destination. 

SOCRATES: So, the Client's request has finally reached the Server?

TED: Yes! 

SOCRATES: How does the Server respond?

TED: There are a few main components to the Server's response. One of the key components is the *Status Line*, which contains the HTTP status code and its description. There are about fifty-something status codes, but there are four categories that are important to remember: (1) `200-299` means success! The `200 OK` is the most common. (2) `300-399` means a redirect. These aren't errors, just that the requested resource is somewhere else so we need to be redirected to it. (3) `400-499` are errors and generally mean that the Client has made an invalid request. (4) `500-599` are also errors but signify that something's wrong with the Server. 

SOCRATES: Ok, that's pretty straightforward. 

TED: The next lines in the response are the headers followed by the body, which typically includes an HTML file, as well as many other files (JS, CSS) and other data. All that data travels through all those layer in their respective PDUs once again, processed and controlled by the various protocols at each layer, until it reaches the Client/browser. If the trip is successful, the Client/browser accepts all of that data and renders a web page for the user on the Client side of our request-response cycle. Then, ta-da! Our user can learn all about you, Socrates, and the history of philosophy! 

SOCRATES: Wow! Full-circle, eh?

TED: Yep, and as I said earlier, all of this typically happens in a fraction of a second. 

SOCRATES: That seems like quite a powerful technology!

TED: It's ubiquitous in my era! I can attend school, pay my bills, order groceries, schedule my doctor appointment... uh, I do pretty much everything over the internet. It's totally excellent, dude! 

SOCRATES: And, everyone has access to it? 

TED: Well, most people do. And, it's becoming more and more accessible every year!

SOCRATES: Umm, yeah, that's good I guess. 

TED: You don't seem so sure. What's on your mind, Socrates?

SOCRATES: Well, you just mentioned that you do everything on the internet. Don't you worry about thieves or frauds? 

TED: Oh yeah, I totally forgot to tell you about *HTTPS* and security. My bad! Looks like we have one more topic to talk about before I jet back to the future. 

SOCRATES: Alright, I have a little more time to chat before I head to the theatre. My buddy, Aristophanes, is premiering his new comedy tonight. 

TED: Ok, let's dive in then. First, let me start off by saying that security is a huge topic and I'm not going to cover all of the ways that a system or protocol can be vulnerable or all of the techniques used to ensure secure, reliable transmission and data integrity. That would take too long and I know you've got places to be, Socrates. 

SOCRATES: That's fine. What do you want to discuss then?

TED: Let's focus on the *Transport Layer Security (TLS)*, a protocol which was initially called the *Secure Sockets Layer (SSL)*. It provides three important security services: (1) *encryption*, (2)*authentication*, and (3) *data integrity*. Let's start with encryption.

SOCRATES: Is that like a secret code?

TED: Yeah, sort of. Within the TLS, it signifies a process of encoding a message so only those who are authorized to decode it can do so and read the message. The way this is implemented is with *the TLS handshake*. 

SOCRATES: Does that happen in place of the TCP three-way handshake?

TED: No, it actually happens after that initial connection is established. If the URL scheme is *HTTPS* - that is, *Secure HTTP* - instead of HTTP, then there will be another handshake after the TCP handshake, which ensures that all subsequent messages between the Client and the Server are encrypted and it also authenticates the Server (or host). 

SOCRATES: So, how does this TLS handshake work? 

TED: It's a little complicated but here's the big picture. First, the Client/browser sends a message to the Server/host to tell the latter what version of TLS it supports and which *cipher suites* it can use. 

SOCRATES: What's a cipher suite?

TED: It's a set of cryptographic algorithms. 

SOCRATES: Ok, I get the picture. 

TED: Once the handshake is initiated with that first `ClientHello` message that I just described, the Server/host responds with the `ServerHello` message which confirms the version of TLS and the ciphers that'll be used. In addition, the Server/host also sends its *public certificate* and its *public encryption key*. 

SOCRATES: Can you say a bit more about those?

TED: Sure! The certificate is used to authenticate the host and the public key is used to decode that initial encrypted message. After those are sent, the Server/host also sends a `ServerHelloDone` message. Then, the Client/browser uses both of these to confirm the identity of the host. If everything checks out, the Client/browser sends a message that determines how the two sides will decide on a *private symmetric encryption key* that they'll use to send and receive all future messages. The Server/host sends a final message to confirm the use of the private symmetric key. 

SOCRATES: So, it's more back-and-forth after the TCP handshake. That must come at a cost, right? I mean, in terms of performance?

TED: For sure, dude! But the TLS handshake is really important as it serves to (1) establish the version of TLS and the specific ciphers that will be in use during the message exchanges, (2) establish trust between the Client and the Server, and (2) create a symmetric key for encrypting and decrypting the messages they send back and forth to one another. That makes the channel of communication both really reliable and really secure. 

SOCRATES: That makes sense. Can you tell me a little bit more about how the Client verifies the identity of the Server/host? 

TED: That has to do with authentication and involves *certificates*. As I mentioned earlier, the Server/host sends a message to the Client/browser with its *certificate* and a *public key*. The Client/browser then looks at the Server/host's signature on the certificate with the provided public key to confirm the Server/host's identity. It's similar to when you're going through security at the airport. The security guard has to scan your passport to verify your identity. 

SOCRATES: Wut? 

TED: Oh yeah, I guess you're not familiar with airports and airplanes. Never mind! 

SOCRATES: No worries. I don't understand your analogy but I think I get the gist. Although, isn't it still possible for the Server/host to have a fake certificate with a fake signature? How does the Client/browser discern whether the Server/host is actually authentic or just an impersonator?   

TED: Great question! The Client can trust the Server because its certificate is also signed by another party, an *intermediate Certificate Authority (CA)*. Now, you might say, why would the Client trust that intermediate? Well, that intermediate authority's certificate is signed by a *root CA*, such as GlobalSign, that is widely recognized to be legitimate and trustworthy. So, since the Client/browser trusts GlobalSign (the root CA), and GlobalSign has given its stamp of approval to the intermediate CA, which has, in turn, approved the Server/host's certificate, it creates a *chain of trust*. Trust is transitive in this case.

SOCRATES: But, it's not a 100% foolproof process against frauds and cheats. 

TED: Well, no, I guess not. But a wise man once said: "Trust must bottom out somewhere. This isn't a Hobbesian state of nature!"

SOCRATES: I accept that. So, what's next? Now, both parties trust each other so they start to exchange encrypted messages, right?

TED: That's right. Now that they're buddies who trust each other, the Client/browser uses the Server/host's public key to send an *encrypted pre-master secret key*. (This is part of the `ClientKeyExchange` message by the way.) The Server/host uses its own private key to decrypt that key so that they both have the pre-master secret key. Once they both have that, they use it (and some other shared parameters) to generate the same *symmetric key* using their agreed-upon cipher (which the Client indicates with the `ChangeCipherSpec` flag). The symmetric keys are then used for their encrypted communication. The Client/browser also sends a `Finished` flag to indicate that the TLS handshake is now completed. 

SOCRATES: That's a very thorough explanation, thanks! I think I'm starting to develop a deeper understanding of the TLS handshake. But, what about that third thing you mentioned with respect to the TLS? Something about integrity?

TED: According to the TLS protocol, the HTTP request is encapsulated into a *TLS record*. The Client/browser uses the symmetric key to encrypt its request, which becomes the body or the *payload* of the TLS record. At each level, the payload tends to come along with *header fields* and footers or *trailer fields*. The header fields of the TLS record contain meta-data (data about its content), such as the version of the TLS protocol in use and the length of the message. 

SOCRATES: Umm, makes sense. [Socrates nods along.] What's in the trailer field then?

TED: What's in the trailer field is the important bit to understand how the TLS ensures data integrity. In that part of the TLS record, we find the *Message Authentication Code*, aka the *MAC footer*. 

SOCRATES: So, how do MAC footers ensure data integrity?

TED: Well, remember in the initial stage of the TLS handshake, the Client and the Server decide on which cipher suite they will use?

SOCRATES: Yeah, and...?

TED: The cipher suite that the Client and the Server agreed on during the TLS handshake contains a *hashing algorithm and initial hash value*, which are used to generate a *digest* of the data payload, which is sent along in the MAC field/footer. The sender sends this digest along with the data that has been encrypted with the symmetric key. The receiver then decrypts the data using that same key, and also derives a digest using the same hashing algorithm and hash value. The receiver's return value for the the digest will be distinct from the MAC _if_ the message is changed in any way. This allows for the receiver of message to check whether the HTTP message has been altered or tampered with in any way during transit. 

SOCRATES: How so exactly?

TED: Well, even _if_ a cheater found a way to alter the encrypted HTTP message, they wouldn't have access to the symmetric key, right?

SOCRATES: Right. 

TED: So, without that key, they wouldn't be able to change the MAC field appropriately. In that case, the MAC that is sent and the MAC that the receiver derives would no longer be identical, and the two parties would be alerted that something fishy is going on.

SOCRATES: Got it!

TED: Also, notice here that because the legitimate receiver must be a holder of the symmetric (private) key to derive the matching MAC, this process also serves to authenticate the receiver. 

SOCRATES: Cool cool cool!

TED: And, one last thing to note is that this process of verification is a little different than what we call the *`checksum` field* in some of the other layers of abstraction. By the way, some models of the internet (e.g. the OSI model) place the TLS in the *Session Layer* between the *Application Layer* and the *Transport Layer*. Or, you can also think about the TLS as operating between HTTP and TCP. 

SOCRATES: Ok, so what's a `checksum`?

TED: Well, I didn't mention this earlier but the PDUs in other layers have checksums to test whether some data was corrupted or lost during transit. For example, the TCP segment contains a checksum intended to detect errors in the data during transport. In a sense, it's a very similar concept to the MAC field in the PDUs of the TLS but the MAC field is intended to provide an added layer of security by checking if the data has been altered. 

SOCRATES: That seems like a pretty robust system of communication. Is there anything else I should know about the Internet? 

TED: Oh, there are many more topics we can talk about. We've merely scratched the surface! But, I know you have to get going. You can't be late to the theater. 

SOCRATES: Oh, that's right! Well, it was nice to meet you, Ted. Have a nice trip back to the future!

TED: Thanks, Socrates, my dude! [Ted high-fives Socrates.]

SOCRATES: Oh, and by the way, in a few years, you'll meet this dude, Bill, on your first job as a software engineer. You and Bill will eventually have great success with your AI startup, and shortly after that, you'll create another technology even more revolutionary than the internet. Anyway, I don't want to spoil it for you but make sure to say hi to Bill for me! See ya!! 

***

[footnote1] - `GET` and `POST` are probably the two most common HTTP request methods. When you type a URL into your browser, that's a `GET` request. When you hit submit on a form, that's (usually) a `POST` request. The big difference between `GET` and `POST` is that the former is never supposed to change anything on the server. 

[footnote2] - Here's the anatomy of a URL:
Let's work with this example: `https://plato.stanford.edu/entries/socrates/#Bib`
1) the *scheme*: this is the protocol to use for the request. Encrypted or secure (`https`), insecure (`http`), or something else entirely, such as the File Transfer Protocol (`ftp`).
2) the *domain*: this is /where/ to send the request. For `HTTP(S)` requests, the `Host` header gets set to this (Host: "plato.stanford.edu").
3) the *port*: this defaults to `80` for `HTTP` and `443` for `HTTPS`
4) the *path*: this is the *Path* to ask the server for. The path and the query parameters are combined in the request. In our example, this is: `/entries/socrates/`. We don't have query parameters here, but an example could be something like: `/entries/socrates?age=young.
5) the *query parameters*: these are usually used to ask for a different version of a page. (see example above)
6) the *URL encoding*: URLs aren't allowed to have certain special characters like spaces, @, etc. So to put them in a URL, you need to percent-encode them as: `%` + hex representation of ASCII value. For example, a space is `%20`, and an actual `%` is `%25`. 
7) the *fragment ID*: this isn't sent to the server at all. It's used either to jump to an HTML tag or by JS on the page. In our example, `/#Bib` is a fragment ID. 

[footnote3] - *IP Addresses* are logical and hierarchical. In IPv4, they are composed of 4 numbers (between 0 and 255) separated by dots. In our example, the IP address is `171.67.193.20`. This address is unique and is used to locate a source or destination on the internet. 
The way an IP address is assigned to a device is determined by a network hierarchy, which is split into logical subnetworks that are defined by the range of IP addresses that are available to them. So, there can be a single local network that includes all addresses in the range `171.67.193.0` to `171.67.193.255`. The first address in the range is referred to as the *network address* and the last one is referred to as the *broadcast address*. Any addresses in between can be assigned to the devices on the network. 

[footnote4] - When you enter a URL in your browser, your ISP will notice the domain name and it will send out a request to the DNS servers for the IP address. The *Domain Name System* reads the domain (or domain name) from right to left. So, for example, when requesting something from `plato.standford.edu`, the request will first go to one of the `root` nameserver delegates, such as the `.edu` nameserver. The `.edu` nameserver will then delegate to the `stanford.edu` nameserver, which in turn delegates to the subdomain `plato.standford.edu` nameserver, which will finally look up and return the correct IP address. 
 
[footnote5] - *Packets* are the Protocol Data Units (PDUs) within the Internet Protocol (IP), which takes place at the Network Layer. As with the other PDUs, it contains a data payload and meta-data in its header fields. The packet's data payload is the PDU from the Transport Layer (that is, a TCP segment or a UDP datagram). The data in a packet is in bits, which is logically separated into the header fields and the payload by the set size of each field in bits and their order within the packet. 
There are a few headers that are important to remember:
1) *Version* - indicates the version of IP (e.g. IPv4 or IPv6)
2) *ID, Flags, Fragment Offset* - "If the Transport layer PDU is too large to be sent as a single packet, it can be fragmented, sent as multiple packets, and then reassembled by the recipient."
3) *Time-to-Live (TTL)* - used to determine the max number of network "hops" a packet can make before it's dropped. So, each time the packet makes a "hop", the TTL value is decremented by 1. At 0, the packet is dropped. This is to make sure that packets that don't reach their destination don't just keep bouncing around in the network. 
4) *Protocol* - indicates the kind of data payload (e.g. TCP segment or UDP datagram).
5) *Checksum* - an algorithm that generates a value used to check whether any errors occurred in the data during transmission. The destination uses the same algorithm to generate the value. If the two values don't match, the packet is dropped. 
6) *Source Address* & *Destination Address* - each of these is 32-bit IP addresses that represent the sender and the receiver of the packet, respectively.

[footnote6] - Latency is an important characteristic of networked communication. 
*Latency* measures the total time it takes for data to get from one point to another in a network.
*Bandwidth* is the amount of data that can be sent in a specified unit of time (e.g., a second). 
- To calculate latency: If the distance between two points is 10 miles, and the speed at which you're traveling is 50 miles/hour, it would take 12 minutes to travel from one point to the other. 
FORMULA: [10 / (50/60)] = 12 [*the ratio between distance and speed*]
You have a latency of 12 minutes!
- The elements of latency are:
1) *Propagation delay* - basically, the ratio between distance and speed; it measures the total time it takes for data to get from one point to another.
2) *Transmission delay* - the time it takes to push the data onto a "link"; that is, when the data has to cross a switch, router, or other network device during its journey. 
3) *Processing delay* - the time it takes for the data to be processed when it is crossing one link to another on the physical network.
4) *Queuing delay* - the time that the data is waiting in a queue in a network device, such as a router. This happens because network devices, like routers, can only process a certain amount of data at one time. When they exceed that amount, they queue or buffer the data. 
The *total latency* between the Client and the Server is the sum of all of these delays in milliseconds.  
- The types of latency are:
1) *Last-mile latency* - A lot of delays occur closest to the end points of transmission. At the edges of a network, there tends to be more frequent "hops" that can lead to more interruptions for transmission, processing, and queuing. This phenomenon is referred to as "last-mile" latency. 
2) *Round-trip latency* - the time for a signal to be sent PLUS the time for an acknowledgement to be received by the sender 








 




















 


