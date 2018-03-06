# Concept
  + States:
    Represent a situation of a smart contract, a state can be a terminate state, an authorization  state or an intermediate state which named by the contract creator.
    An authorization  state is embraced by angle brackets.

  + Events:
     Represent an action that changes a state. There are multiple pre-defined events available.
     There is a special event called termiante. With

# Events
+ transaction_event
  Use case: A contract creator assigns a receiving account to accept an certain amount of money.

  Grammar: receiving transaction of INT to FEATHERACCOUNT

  Example: receiving transaction of 100 to feth233dbc320699

+ signing_event

  Use case: The target users accept one or more aggrements required by a contract creator.

  Grammar: accepting license ID (,ID)*

  Example: accepting license e759419923ea25bf6dff2694391a1e65c21739ce,e759419923ea25bf6dff2694391a1e65c21739ce
+ period_event

  Grammar: on end of INT TIMEUNIT

  Example: on end of 3 cycles

+ specific_date_event

  Use case: A certain time is reached.

   Grammar: at YYYY-MM-DD HH:MM(:SS)?

   Example: at 2012-12-12 12:12:12

+ relative_date_event

  Use case: When a period of time has gone.

  Grammar after INT TIMEUNIT of contract creation

  Example : after 1 cycle of contract creation

+ contract_guaranty_event

  Use case:  When the target user deposit a certain amount of money to the supervised account.

  Grammar: 'contract_guaranty of' INTEGER_NUMBER 'refund after' INTEGER_NUMBER TIMEUNIT

  Example: contract_guaranty of 100 refund after 3 days


+ platform_guaranty_event

  Grammar: on receiving platform_guaranty of INT

  Example: on receiving platform_guaranty of 100

+ visit_increment_event

  Use case: The resource was viewed upon accumulation of a certain amount of views.

  Grammar: 'visit_increment of' INTEGER_NUMBER

  Example: visit_increment of 123

+ visit_event

  Grammar: 'visit of' INTEGER_NUMBER

  Example: visit  of 123 
+ pricing_agreement_event
  pending

# Types
 +  Enumerate
    + TIME_CYCLE

      day, week ,year, cycle

    + SYSTEM GROUP

      self: refers to author himself/herself

      nodes: refers to all nodes

      public: every one




  +  Regular Expression
    + FEATHERACCOUNT

       FEATHERACCOUNT is an account, it is either a 13-digit phone number or e-mail address.

       Regular Expression :^f[a-zA-Z0-9]*;

    + INTEGER_NUMBER

       INTEGER_NUMBER is non-negative integer.

    + ID

        ID are symbols that includes Upper Case, lower case or underscore.

        Regular Expression :[<>_a-zA-Z]+;

    + USER GROUP

        USER GROUP is a group of users.

        Regular Expression : group_user_[a-zA-z0-9]{4}

    + USER NODE

        USER NODE is a group of nodes.

        Regular Expression : group_node_[a-zA-z0-9]{4}


# Reserved words
  * for: followed by user group, node group, domain name, or system gruop

  * initial: a initial state of a smart contract, every contract starts with state **initial **

  * proceed to: followed by a state name

  * on: followed by an event name
