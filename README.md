
# Creating Addresses

#### Exercise Find the output address corresponding to this ScriptPubKey
```
76a914338c84849423992471bffb1a54a8d9b1d69dc28a88ac
```

Remember the structure of pay-to-pubkey-hash (p2pkh) which has `OP_DUP OP_HASH160 <hash> OP_EQUALVERIFY OP_CHECKSIG`.

You need to grab the hash160 and turn that into an address.


```python
# Exercise 3.1

from helper import h160_to_p2pkh_address
from script import Script

hex_script_pubkey = '76a914338c84849423992471bffb1a54a8d9b1d69dc28a88ac'

# bytes.fromhex to get binary
# parse with Script
# get the 3rd element, which should be the hash160
# convert h160 to p2pkh address
```

### Test Driven Exercise


```python
from script import Script
from helper import h160_to_p2sh_address

class Script(Script):

    def address(self, testnet=False):
        '''Returns the address corresponding to the script'''
        sig_type = self.type()
        if sig_type == 'p2pkh':
            # hash160 is the 3rd element
            # convert to p2pkh address using h160_to_p2pkh_address (remember testnet)
            pass
        elif sig_type == 'p2sh':
            # hash160 is the 2nd element
            # convert to p2sh address using h160_to_p2sh_address (remember testnet)
            pass
```
