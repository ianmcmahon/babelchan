Start here to understand the concept of http://libraryofbabel.info/theory.html

Any text that can exist already, in a sense, exists.  If you create original content which exists within the library of babel, can you not merely point to that page in the library and deem it prior art?

babelchan aims to be a chan-style anonymous message forum built upon a blockchain, where messages are encoded to an index into library of babel.  This provides some interesting options for obscuring content: the babel algorithm provides consistent two-way hashing based on a seeded PRNG, and using the same seed is required to get a round-trip back to the original cleartext.

The babel encode/decode should happen on the client side; it's fairly straightforward and not terribly resource intensive for small quantities of decodes, but would be impractical to scale for server side decoding, plus this gives a lot of insulation for the nodes hosting the chain, as there's no decodable content on the chain itself, only "encrypted" data which can only be decrypted with the appropriate seed.

This gives rise to the idea of groups, where the group maintains a shared seed that isn't publically available.  Only clients with the proper seed for the group can decode any messages.  Any thread or individual message could be encoded with an arbitrary seed to control visibility.

As important as free speech is for a platform like this, moderation is always necessary.  I believe moderation works best when handled in small communities, and could potentially work especially well when wrapped in an economic system where market forces dictate the rules of the game rather than arbitrary policies, obfuscated AI metrics, and "trust and safety" teams.

I have some ideas for how to build an economy that will benefit users exclusively, and provide some interesting emergent behaviors as people learn how to carve their own piece of that economy.

First, it is important to note that moderation would be entirely within the realm of the Client (website/app/whatever UI), and since the idea is to run this as a completely decentralized system, there is nothing preventing multiple clients from presenting the data contained within the chain, assuming it has enough information to do so.  If there is a defacto "official" client where content is created and viewed, it can implement whatever policies it prefers for moderation or content filtering, and others are just as free to create alternative clients which display the chain in any capacity they would like.  The chain itself contains no meaningful data without knowledge of the babel seed used to post it.

The blockchain itself is structured similarly to bitcoin's, with some additional fields in transactions which contain the index into babel that represents the encoded message.  Messages are always sent as replies, meaning they are directed at a particular user or message, and that encodes the tree structure of forum threads.  This also allows the poster to optionally send coin to the OP.  There should also be metadata about whether it's an upvote or downvote reply, and the amount of coin donated alongside the reply informs clients as to the weight it should apply to the action.  If someone gives you a lot of money to upvote your content and reply, then their reply could be thought of like the "superchat" model, where they wanted you to see what they said enough that they've outbid other people vying for your attention.   If someone is posting negative comments and/or downvotes, they can amplify the weight of their disapproval by GIVING YOU MONEY for the privilege of their dissent being more visible.  Dislike brigades are a real thing, and there's an economy to it.  If you have an army of people or bots, it costs you essentially nothing to brigade someone's content, but you gain value, or at the very least destroy someone else's value.  By allowing clients to de-emphasize or even ignore negative comments with no money attached, it gives people the ability to dissent if they feel strongly enough that they're willing to exchange some value.

By wrapping an economy around the social capital being exchanged by users, we also give value to the coins created by the blockchain mining process, which gives people an economic incentive to grow and maintain the network.  Users who create content which gets a lot of engagement will inevitably get engagement which people pay to amplify one way or the other, and will earn coins which they can themselves use to participate in the moderation process.  Anyone is free to buy coins on an exchange to trade money for moderation power or social capital, this gives the miners an outlet for their production.





Blockchain implementation forked from https://github.com/Jeiwan/blockchain_go, which is described in the following articles:

1. [Basic Prototype](https://jeiwan.cc/posts/building-blockchain-in-go-part-1/)
2. [Proof-of-Work](https://jeiwan.cc/posts/building-blockchain-in-go-part-2/)
3. [Persistence and CLI](https://jeiwan.cc/posts/building-blockchain-in-go-part-3/)
4. [Transactions 1](https://jeiwan.cc/posts/building-blockchain-in-go-part-4/)
5. [Addresses](https://jeiwan.cc/posts/building-blockchain-in-go-part-5/)
6. [Transactions 2](https://jeiwan.cc/posts/building-blockchain-in-go-part-6/)
7. [Network](https://jeiwan.cc/posts/building-blockchain-in-go-part-7/)
