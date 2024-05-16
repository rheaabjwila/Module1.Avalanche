// SPDX-License-Identifier: MIT
pragma solidity ^0.8.25;

contract CombinedExample {
    mapping (address AccAddress => uint StoredAmount) public ShowBalance;
    uint StoredAmount;

    function deposit(address Acc, uint256 amount) public {
        require(amount > 0 && amount <= 1000, "Amount must be between 1 and 1000 inclusive");
        ShowBalance[Acc] += amount;
        StoredAmount += amount;
    }

    function withdraw(address Acc, uint256 amount) public {
         if (amount <= 0 || amount > 1000) {
            revert("Amount must be between 1 and 1000 inclusive");
        }
        assert(amount <= ShowBalance[Acc]);
        ShowBalance[Acc] -= amount;
        StoredAmount -= amount;
    }
}
