SUAPP security audit report performed by Callisto Security Audit Department
1. Conclusion:
The Token contract is safe to be deployed. But the token description do not fully match the implementation - token is not Burnable.

2. High severity issues:
No High severity issues

3. Medium severity issues:
No Medium severity issues

4. Low severity issues:
4.1. Known vulnerabilities of ERC-20 token
Description
It is possible to double withdrawal attack. More details here
Lack of transaction handling mechanism issue. More details here
4.2. Token Burnability
Description
Following the token description provided by the developers SUAPP token should be burnable.
SUAPPToken does not inherit from BurnableToken, therefore the token description is not valid since no burn function is implemented or inherited from BurnableToken.

Code snippet
https://gist.github.com/RideSolo/63a226868ca720f60b320cc4032728c9#file-suapp-sol-L108

https://gist.github.com/RideSolo/63a226868ca720f60b320cc4032728c9#file-suapp-sol-L335

5. Minor observation:
5.1. Reclaim Token
Description
The description of reclaimToken function is unclear, the implemented function allows any token with a certain value that is sent to SUAPP token contract to be transfered to SUAPP contract owner.

Code snippet
https://gist.github.com/RideSolo/63a226868ca720f60b320cc4032728c9#file-suapp-sol-L328#L331

5.2. Extra checking
Description
Extra checking in 88, 117, 160, 161 lines. SafeMath library checks it anyway.

Recommendation
Those lines may be deleted.

Revealing audit reports:
https://gist.github.com/yuriy77k/0b2df5d5550ae664e3ba820324680016

https://gist.github.com/yuriy77k/b6b6fe245aed49bff8758a96da930f89

https://gist.github.com/yuriy77k/946b1774955e11f5116e39c8f476b855
