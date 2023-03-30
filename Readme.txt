////////////////Smart Contract////////////////////

//SPDX-License-Identifier: MIT

// Declaración de la versión del compilador de Solidity
pragma solidity ^0.8.0;

// Declaración del contrato
contract MiContrato {
    
    // Variables del contrato
    uint256 public miVariable;  // una variable pública
    
    // Eventos
    event MiEvento(address indexed _from, uint256 indexed _value); // un evento
    
    // Constructor
    constructor() {
        miVariable = 100; // establece el valor inicial de la variable miVariable en 100
    }
    
    // Funciones del contrato
    function setVariable(uint256 _newValue) public { // una función pública que actualiza el valor de miVariable
        miVariable = _newValue; // actualiza el valor de miVariable
        emit MiEvento(msg.sender, _newValue); // emite un evento MiEvento con el emisor de la transacción y el nuevo valor
    }
    
    function getVariable() public view returns (uint256) { // una función pública que devuelve el valor actual de miVariable
        return miVariable; // devuelve el valor actual de miVariable
    }
}

/////////EXPLICACIÓN DE LA ESTRUCTURA DEL SMART CONTRACT //////////////////////////////

se comienza colocando como comentario declarando la licencia //SPDX-License-Identifier: MIT

Este contrato sigue la estructura básica de un contrato de Solidity:

Comienza con la declaración de la versión del compilador de Solidity en la primera línea del contrato.

Luego se declara el contrato con su nombre, MiContrato.

Dentro del contrato, se declaran las variables que se utilizarán en el contrato. En este caso, solo hay una variable pública llamada miVariable.

Después de las variables, se declara el evento MiEvento, que se utilizará para registrar información en la blockchain de Ethereum.

A continuación, se declara el constructor del contrato, que se ejecutará cuando el contrato se despliegue en la blockchain.

Después del constructor, se declaran dos funciones públicas: setVariable y getVariable. La función setVariable actualiza el valor de miVariable y emite el evento MiEvento, mientras que la función getVariable devuelve el valor actual de miVariable.

En general, esta es la estructura básica de un contrato inteligente en Solidity.

//////////////////////////// Desplegar el contrato/////////////////////////////////////

Para publicar el contrato usar Metamask en la red Testnet de Goerli. Previamente solicitar Ether en algún faucet de Goerli (https://goerlifaucet.com/).

En ENVIROMENT escoger Injected Provider - Metamask, lo cual conectará el IDE de Remix con una billetera de Metamask.

En CONTRACT asegurar que está seleccionado el contrato que se desea publicar

Al hacer clic en Deploy, abrirá un pop-up de Metamask para poder confirmar y firmar la transacción, lo cual hará posible la creación del Smart Contract en el Blockchain.

Cuando la transacción haya terminado, se podrá visualizar dentro de la pestaña de Actividad. Hacer click en Implementación de contrato y se abrirá otra ventana. En dicha ventana hacer click en Ver en el explorador de blockes.

