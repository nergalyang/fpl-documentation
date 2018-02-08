
# What is FPL (Freelog Policy Language)?
  FPL is a declarative language built for creating smart contracts that compile to into finite-state machine. With the help of FPL, a resource/node owner can customize the authorization model to their valuable intellectual products by restricting access groups, proposing terms and conditions, and enforcing payment or profit splitting plans. The language grammar (created with antlr4) is available on [github](https://github.com/nergalyang/freelog-policy/blob/master/policy.g4).





# FPL grammar
  The grammar of FPL was designed to be simple. In smart contract, there're three types of objects need to be defined or specified:
   * Users or user groups whom to be authorized
   * States that represent different stages of the authorization process
   * Events that trigger state transitions

   FPL grammar has corresponding components: audience_clause, transition_clause.

  * Audience_clause: It describes the users. Begins with the key word **For** and followed by target users. They are users, user groups, and system reserved groups whom to be authorized.
  * Transition_clause: It describes the states and events. Begins with the key word **in** + an initial state, followed by the key word **proceed to** + the next state, and ends with the key word **on** + events.

  In transition_clause, we can define authorization state where we grant access to users, authorization states are embraced by angle  brackets **<>**.eg: \<authorization>.


# Create your first smart contract.

  Let us begin with the most basic example. It is fine if you do not understand everything right now, we will go into more detail later.
  ## Overview
  The following is a smart contract for a image owner who wants to sell his image on  [www.freelog.com](www.freelog.com).
```
    1.  fpr public:
    2.    in initial:
    3.      proceed to <activate> on accepting transaction of 100 to 0xf1234354
```
The above smart contract means that every one of freelog.com has the right to sign this contract, once the contract is executed, the contract will be in the initial state. Now the contract is waiting for an transaction event. At any time, if a transaction to the ether address 0xf1234354 is done, the contract will move to a state named activate which is an authorization state. Now the contract is available to the user who executed the contract.

##Grammar in depth
      1.  for public :
  This is an audience_clause.The first line declares **public**[[*system reserved group*](www.freelog.com)] that have access to your resource. There are three types of users. One is individual user specified by [user ID](www.freelog.com), one is user group sepcified by limited user group names, another is system reserved group. User ID is given when you create your freelog account. System reserved groups are : **public**, **nodes**, **self**, and etc.

      <activate>
  The line is an authorization state. It determines the authorized state, meaning that users have access to your resource in state **\<activate>**[[ID](www.freelog.com)]. You can choose any state to be your authorized state as long as they are occurred.
  ```
    2.    in initial :
    3.      proceed to <activate> on accepting transaction of 100 to 0xf1234354
```

  Above is a transition_clause, which shows the contract states change. The starting transition always start with an initial [state]() called **initial**. State transitions are descriptions for state machine. They tell users what is their current state, what [events]() move them to the next state. Line 2 declares current state names **initial**. The corresponding next state is **activate** in line 3 and line 5  .  The line **transaction of 100 to 0xf1234354**[[*FEATHERACCOUNT*](www.freelog.com)] represents an event of
  paying 100 to an account 0xf1234354.

  Once the example contract is executed, the current state is initial. As long as the transition rule is satisfied by a visitor, the contract'll move to state **\<activate>** which is an authorized state. The visitor will have the right to access to your resource.
