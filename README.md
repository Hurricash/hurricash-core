# Hurricash PulseChain Privacy Solution [![Build Status](https://app.travis-ci.com/Jinchans/Hurricash.svg?token=zLmEi2vhCjnHEtz9GPyz&branch=master)](https://app.travis-ci.com/Jinchans/Hurricash)

Hurricash is a non-custodial ERC20 privacy solution based on the LSAG algorithm. It serves as a second layer of privacy and/or alternative to other privacy solutions such as Tornado Cash. It improves transaction privacy by breaking the on-chain link between the recipient and destination addresses. It uses a smart contract that accepts ERC20 deposits that can be withdrawn by a different address. Whenever the ERC20 is withdrawn by the new address, there is no way to link the withdrawal to the deposit, ensuring complete privacy.

To make a deposit user selects the reciever address and choses the incremental ammount then generates a secret "hcash token". The deposit amount is then sent to the Hurricash smart contract. The contract accepts the deposit and adds the key as valid to the corresponding ring signature pool list of deposits.

After enough time has passed and sufficient users have entered the pool, the user can decide to make a withdrawal. To do that, the user should provide a proof that he or she possesses the secret hcash token as well is using the correct public key address to withdraw.

LSAG technology allows that to happen without revealing which exact deposit corresponds to this secret. The smart contract will check the proof, and transfer deposited funds to the address specified for withdrawal. An external observer will be unable to determine which deposit this withdrawal came from.
