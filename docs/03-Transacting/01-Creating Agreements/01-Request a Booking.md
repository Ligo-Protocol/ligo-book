---
title: "Request a Booking"
---

## 1. Renter requests a booking
A booking is created by the renter first creating a [LigoAgreement](../../Reference/Schema/LigoAgreement). This should be generated from the vehicle offer to ensure it meets the baseline requirements set by a host.

The renter then creates a Safe with themself as the sole signer and deposits the initial amount of funds specified in the agreement.

![Create a Booking 1.excalidraw](../../drawings/Create%20a%20Booking%201.excalidraw.svg)

The renter then adds the Ligo safe module to the safe. Once that is complete, they add the host as a signer of the safe with a 2 of 2 threshold. The safe module will allow the renter to withdraw funds as long as an agreement has not been added.

The agreement, along with a signature from the renter to update the agreement is sent to the host to review.

![Creating a Booking 2.excalidraw](../../drawings/Creating%20a%20Booking%202.excalidraw.svg)

## 2a. Host accepts booking
If the host would like to accept the booking, they should also sign the transaction to add the agreement to the Safe. Either party can now execute the transaction.

![Create a Booking 3.excalidraw](../../drawings/Create%20a%20Booking%203.excalidraw.svg)

## 2b. Host rejects booking
If the host would like to reject the booking, they can immediately send a transaction to the safe module. Otherwise, if there is no response to the request the renter may choose to withdraw their funds at any time.

![Reject Booking.excalidraw](../../drawings/Reject%20Booking.excalidraw.svg)

## 2c. Further changes
The host can also respond with changes to the agreement by sending a new transaction of the same nonce with a new CID.

## 3. Agreement is in effect
Once both parties have signed the transaction to update the agreement, the agreement goes into effect and the Ligo Module will now follow the rules laid out in the agreement.

---
## Appendix
### Open Questions
- How is the agreement sent to the host?
	- Waku or XMTP (more private?)
	- Safe transactions service