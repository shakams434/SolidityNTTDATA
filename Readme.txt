////////////////Smart Contract////////////////////

// SPDX-License-Identifier: MIT
pragma solidity 0.6.0;

contract Erc20Basic {
    
    // Variables públicas del token
    string public constant name = "BitCoin";
    string public constant symbol = "BTC";
    uint8 public constant decimals = 18;

    // Crea un mapeo con la cantidad de tokens que cada cuenta posee
    mapping(address => uint) balances;
    
    // Suministro total del token
    uint256 totalSupply_ = 1000000000000000000000;
    
    // Inicializa el token asignando todo el suministro total al creador del contrato
    constructor() public {
        balances[msg.sender] = totalSupply_;
    }
    
    // Función para obtener el suministro total del token
    function totalSupply() public view returns(uint256) {
        return totalSupply_;
    }
        
    // Función para obtener el saldo de una cuenta
    function balanceOf(address account) public view returns(uint256) {
        return balances[account];
    }
        
    // Función para transferir tokens
    function transfer(address recipient, uint256 amount) public returns(bool) {
        // Comprueba que el remitente tenga suficientes tokens para transferir
        require(amount <= balances[msg.sender]);
        // Resta la cantidad de tokens del remitente
        balances[msg.sender] = balances[msg.sender]-amount;
        // Agrega la cantidad de tokens al destinatario
        balances[recipient] = balances[recipient]+amount;
        // Registra la transferencia de tokens
        return true;    
    }
    
}

//////////////////////////////////////////////////////////////////////////////////


NOTAS:


//////////////////////////// Desplegar el contrato/////////////////////////////////////

Para publicar el contrato usar Metamask en la red Testnet de Goerli. Previamente solicitar Ether en algún faucet de Goerli (https://goerlifaucet.com/).

En ENVIROMENT escoger Injected Provider - Metamask, lo cual conectará el IDE de Remix con una billetera de Metamask.

En CONTRACT asegurar que está seleccionado el contrato que se desea publicar

Al hacer clic en Deploy, abrirá un pop-up de Metamask para poder confirmar y firmar la transacción, lo cual hará posible la creación del Smart Contract en el Blockchain.

Cuando la transacción haya terminado, se podrá visualizar dentro de la pestaña de Actividad. Hacer click en Implementación de contrato y se abrirá otra ventana. En dicha ventana hacer click en Ver en el explorador de blockes.

