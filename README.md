# Flow-proof
#CHALLANGE 1
Writing FIRST smart contract using Cadance
# Challange Description
This project has leveraged fundamental functions and variables introduced across various modules using Cadence. The primary objective of this endeavor is to gain a solid understanding of structs and arrays within programming contexts.
# Getting Started
# Executing program
To run this program, you can use flow-playground, an online cadence IDE. To get started, go to the play.flow website at https://play.flow.com/
////CONTRACT//////
pub contract challenge
{
pub var cars: {Address:car}
  pub struct car 
  {
    pub let model: String
    pub let year: UInt
    pub let owner: Address
    init(_model: String, _year: UInt, _owner: Address)
     {
        self.model = _model
        self.year = _year
        self.owner = _owner
     }
  } 
  pub fun carone(model: String, year: UInt, owner: Address)
  {
      let cartwo =car(_model: model, _year: year, _owner: owner)
      self.cars[owner]=cartwo
  }
   init() {
        self.cars = {}
    }
}
/////TRASACTION////
import challenge from 0x05
transaction(model:String, year: UInt, owner: Address) {
  prepare(acct: AuthAccount) {}
  execute {
    challenge.carone(model: model, year: year, owner: owner)
    log("modified")
  }
}
////SCRIPT/////
import challenge from 0x05
pub fun main(owner: Address):challenge.car{
return challenge.cars[owner]!
}
Firstly we write our smart contract by creating a new struct of your liking then create a function that can add to the array. Then we call the function in transaction to modify or add new data into the array.Finally we use script to view the changes we made to the blockchain.

# My Observation 

I thoroughly enjoyed coding with FLOW as well! Initially, the concept felt quite foreign to me, but through practice and exploration, I believe I've grasped the language and its concepts quite well. I'm excited about delving into more modules and courses offered by MetaCrafters to further enhance my understanding and skills in blockchain development.






