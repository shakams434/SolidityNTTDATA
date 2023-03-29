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

/////////
Este contrato define una variable de estado myNumber y una variable de estado myString. También tiene un constructor que acepta un número y una cadena como parámetros y los asigna a las variables de estado correspondientes.

También tiene dos funciones: setNumber y getString. setNumber permite al usuario cambiar el valor de myNumber, mientras que getString devuelve el valor de myString.

El contrato también define un modificador onlyOwner, que se aplica a una función para asegurar que solo el propietario del contrato pueda llamar a esa función.

Finalmente, el contrato define un evento NumberSet que se emite cada vez que se llama a la función setNumber. Este evento registra el nuevo valor de myNumber.
