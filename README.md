# Joint Savings
Joint savings is a solidity program to facilitate transactions between crypto wallet accounts. I was supported by Tutor: Gerrado, received advice from Shah in class (TA), and received help from online resources: 
1.  https://metana.io/blog/require-assert-revert-solidity
2.  https://www.tutorialspoint.com/solidity/solidity_operators.htm

### Code:
The code works in the following way: To deposit and receive ETH from two different accounts. 

#### Step 1: 
Defined variables within function: JointSavings


    pragma solidity ^0.5.0;
    
    contract JointSavings {
    
        address payable accountOne; 
        address payable accountTwo; 
        address public lastToWithdraw; 
        uint public lastWithdrawAmount;
        uint public contractBalance; 

#### Step 2: 
Created functions to withdraw and deposit cash. 
            function withdraw(uint amount, address payable recipient) public {
                require(recipient == accountOne || recipient == accountTwo, "You don't own this account!" );
                require(contractBalance >= amount, "Insufficient Funds!"); // amount is compared to the contract Balance 
                if(lastToWithdraw != recipient){
                    lastToWithdraw = recipient; 
                }
                recipient.transfer(amount); 
                lastWithdrawAmount = amount; 
                contractBalance = address(this).balance; 
            }
        
            function deposit() public payable {
                contractBalance = address(this).balance; 
            }
            function setAccounts(address payable account1, address payable account2) public{       
                accountOne = account1;
                accountTwo = account2; 
            }
            function()
                external payable{}
            


