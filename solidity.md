Blackbox Coding Challenge: Hack The Token Contract
==============================================

Problem Description
-------------------
You've been given the below token smart contract. Your goal is to identify the vulnerabilities and hack the contract to get more tokens.

Submission Instructions:
------------
Once completed, please create a new repository called "Blackbox Hack The Token Contract" under your personal github account. Then email your interviewer a link to the new repo.

Submission Requirements
-----------------------
You should submit a revised contract and a brief explanation (2-3 sentences) of the vulnerability and your plan of action

You may write your program in any of the following languages:

* Solidity (0.4+)

Token Smart Contract
-------------
      pragma solidity ^0.4.23;

      contract Token {

        mapping(address => uint) balances;
        uint public totalSupply;

        function Token(uint _initialSupply) public {
          balances[msg.sender] = totalSupply = _initialSupply;
        }

        function transfer(address _to, uint _value) public returns (bool) {
          require(balances[msg.sender] - _value >= 0);
          balances[msg.sender] -= _value;
          balances[_to] += _value;
          return true;
        }

        function balanceOf(address _owner) public view returns (uint balance) {
          return balances[_owner];
        }
      }
