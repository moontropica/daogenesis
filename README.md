![logo](https://user-images.githubusercontent.com/33762147/185423739-0dd1b17b-bd3f-4ebc-8e3f-0afd90281c2a.png)

# DAO Genesis Event
Specifications for obtaining the initial Moon Tropica DAO members.

Total Proposed Seats: 69
<br>
Reserved Seats by `owner`: 8

DAO Members will be customized characters to reflect their real image in-game and be able to cast votes on behalf of their community.

# Smart Contract Archetecture
To obtain a seat, a member has to be granted a referral from the wallet address `HGEqpS1rRaBEPoRF9qqqkSapfQrUeU2Dr8XDtUVDMf5a`

### Array Structure for `daoList`
|list|address|refAmt|
|----|-------|------------|
|1|`MTWrkFYq4SayCrhBw8BgsPiTVKTDjyV6wRqP7HL9Eyyw`|7|
|2|`HGEqpS1rRaBEPoRF9qqqkSapfQrUeU2Dr8XDtUVDMf5a`|12|
|3|`AtxcnuUcpnT8yn9dRKNUd9EvXckyTHpkEkea9mTLmwqX`|4|
|...|...|...|
|69|`BUbpvUFZTxxQBB5gYYkH1pps1CMtKj4vLnBwMPo1ZcZe`|0|

## Write Functions
|function|vars   |desc  |
|--------|-------|------|
|`setOwner`|account(*address*)|To be set immedately or during deployment. Sets the `owner` of the contract.|
|`addDAO`|account(*address*), refAmt(*uint*)|Can only be called by `owner` of contract or wallet in `daoList` array with `refAmt > 0`, if `refAmt =< 0` throw exception. Subtract `-1` from self refAmt.|
|`remove`|line(*uint*)|Removes line number from `daoList` array. Can only be called by `owner` of contract. Used in-case of issuing a faulty *address*.|

## Read Functions
|function|vars   |desc  |
|--------|-------|------|
|`owner`|account(*address*)|Prints the `owner` of the contract.|
|`daoList`|*view*|Print the *addresses* in the `daoList` array.|

## UI Wireframe

<div align="center">

![index](https://user-images.githubusercontent.com/33762147/185794015-a46dc0d2-0639-4b4f-9607-28a2d8a47939.png)

</div>
