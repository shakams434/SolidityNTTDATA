Smart Contract

pragma solidity ^0.8.0;

contract MyContract {
    // Variables de estado
    uint256 public myNumber;
    string public myString;
    
    // Constructor
    constructor(uint256 _myNumber, string memory _myString) {
        myNumber = _myNumber;
        myString = _myString;
    }
    
    // Funciones
    function setNumber(uint256 _newNumber) public {
        myNumber = _newNumber;
    }
    
    function getString() public view returns (string memory) {
        return myString;
    }
    
    // Modificadores
    modifier onlyOwner() {
        require(msg.sender == owner, "Solo el propietario puede llamar a esta función");
        _;
    }
    
    // Eventos
    event NumberSet(uint256 newNumber);
}
