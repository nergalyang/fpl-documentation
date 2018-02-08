# Concept
  + ##States:
    Represent a situation of a smart contract, a state can be a terminate state, an authorization  state or an intermediate state which named by the contract creator.
    An authorization  state is embraced by angle brackets.

  + ##Events:
     Represent an action that changes a state. There are multiple pre-defined events available.
     There is a special event called termiante. With

# Events
+ ##transaction_event
  Use case: A contract creator assigns a receiving account to accept an certain amount of money.

  Grammar: receiving transaction of INT to FEATHERACCOUNT

  Example: receiving transaction of 100 to 0x12345

+ ##signing_event

  Use case: The target users accept one or more aggrements required by a contract creator.

  Grammar: accepting license ID

  Example: accepting license LicenseResourceId
+ ##period_event
  Grammar: end of TIME_CYCLE

+ ##specific_date_event

  Use case: When a certain time is arrived.

   Grammar: arriving date DATE

+ ##relative_date_event

  Use case: When a period of time has gone.

  Grammar : INTEGER_NUMBER TIME_CYCLE after contract creation

+ ##guaranty_event

  Use case:  When the target user deposit a certain amount of money to the supervised account.

  Grammar: having deposit of INT


+ ##accumulative_view_event

  Use case: The resource was viewed upon accumulation of a certain amount of views.

  Grammar: per INT views

+ ##settlement_event

  pending
+ ##pricing_agreement_event
  pending

# Types
 + ## Enumerate
    + TIME_CYCLE

      day, week, year, cycle

    + SYSTEM GROUP

      self: refers to author himself/herself

      registered_users: refers to users already registered on www.freelog.com

      public: every one

  + ## Regular Expression
    + FEATHERACCOUNT

       FEATHERACCOUNT is an account, it is either a 13-digit phone number or e-mail address.

       Regular Expression :^f[a-zA-Z0-9]*;

    + INTEGER_NUMBER

       INTEGER_NUMBER is non-negative integer.

    + ID

        ID are symbols that includes Upper Case, lower case or underscore.

        Regular Expression :[<>_a-zA-Z]+;


# Reserved words
  * for: followed by individual user, user group, or system gruop

  * initial: a initial state of a smart contract, every contract should start with state **initial **

  * proceed to: followed by a state name

  * on: followed by an event name
