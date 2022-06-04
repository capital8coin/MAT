pragma solidity ^0.8.7;



contract token {

    mapping(address => uint) public balance;

    mapping(address => mapping(address => unit)) public allowance;

    uint public totalSupply = 100000000 * 10 ** 18;

    string public name = "Medusa Artist Token";

    string public symbol = "MAT$";

    unit public decimals = 18;



    event Transfer(address index from, address indexed to, uint value);

    event Approval(address indexed owner , address indexed spender, unit value);



    constructor(

pragma solidity ^0.8.7;



contract token {

    mapping(address => uint) public balance;

    mapping(address => mapping(address => unit)) public allowance;

    uint public totalSupply = 100000000 * 10 ** 18;

    string public name = "Medusa Artist Token";

    string public symbol = "MAT$";

    unit public decimals = 18;



    event Transfer(address index from, address indexed to, uint value);

    event Approval(address indexed owner , address indexed spender, unit value);



    constructor() {

        balances[msg.sender] = totalSupply;

    }



    function balanceOf(address owner) puplic view returns(unit) {

        return balances[owner];

    }



    function transfer(address to, unit value) puplic returns(bool) {

        require(balanceOf(msg.sender) >= value, 'balance too low');

        balances[to] += value;

        balance[msg.sender] -= value;

        emit Transfer (msg.sender, to, value);

        return true;

    }



    function transferFrom(address from, address to, uint value) public returns(bool) {

        require(balanceOf(from) >= value, 'balance too low')

        require(allowance[from][msg.sender] >= value, 'allowance too low')

        balance[to] += value;

        balance[from] -= value;

        emit Transfer(from, to, value);

        return true;

    }



    function approve(address spender, uint value) public returns(bool){

        allowance[msg.sender][spender] = value;

    return true;



    }

} {

        balances[msg.sender] = totalSupply;

    }



    function balanceOf(address owner) puplic view returns(unit) {

        return balances[owner];

    }



    function transfer(address to, unit value) puplic returns(bool) {

        require(balanceOf(msg.sender) >= value, 'balance too low');

        balances[to] += value;

        balance[msg.sender] -= value;

        emit Transfer (msg.sender, to, value);

        return true;

    }



    function transferFrom(address from, address to, uint value) public returns(bool) {

        require(balanceOf(from) >= value, 'balance too low')

        require(allowance[from][msg.sender] >= value, 'allowance too low')

        balance[to] += value;

        balance[from] -= value;

        emit Transfer(from, to, value);

        return true;

    }



    function approve(address spender, uint value) public returns(bool){

        allowance[msg.sender][spender] = value;

    return true;



    }

}
