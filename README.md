# Joint Savings
Joint savings is a solidity program to facilitate transactions between crypto wallet accounts. I was supported by Tutor: Gerrado, received advice from Shah in class (TA), and received help from online resources: 
1.  https://metana.io/blog/require-assert-revert-solidity
2.  https://www.tutorialspoint.com/solidity/solidity_operators.htm

### Code:
The code works in the following way: To deposit and receive ETH from two different accounts. 

#### Step 1: 
Defined variables and 

pragma solidity ^0.5.0;

contract JointSavings {

    address payable accountOne; 
    address payable accountTwo; 
    address public lastToWithdraw; 
    uint public lastWithdrawAmount;
    uint public contractBalance; 

