// SPDX-License-Identifier: MIT
pragma solidity ^0.8.25;

contract LetsBaked {
    string public LetsMakeCookies = "Make some cookies!";
    uint Flour;
    uint Eggs;
    uint ChocoChip;

    function FlourRange(uint Grams) public{
        if(Grams != 5){
            revert("Put exactly 5 grams of flour!");
        }
        Flour = Grams;
    }

    function EggPieces(uint Pieces) public{
        require(Pieces == 2, "The textured will be bad!");
        Eggs = Pieces;
    }

    function ChocoChips(uint Cup) public{
        assert(Cup == 1);
        ChocoChip = Cup;
    }

    function CheckCookies() public {
        if(Flour == 0){
            revert("Add some Flour!");
        }else if(Eggs == 0){
            revert("Add some Eggs!");
        }else if(ChocoChip == 0){
            revert("Add some Chips!");
        }else{
            LetsMakeCookies = "Here's your cookies!";
        }
    }
}
