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

  Grammar: license ID

  Example: license LicenseResourceId
+ ##period_event
  Grammar: end of TIME_CYCLE

+ ##specific_date_event

  Use case: When a certain time is arrived.

   Grammar: arriving date DATE

+ ##relative_date_event

  Use case: When a period of time has gone.

  Grammar

+ ##guaranty_event

  Use case:  When the target user deposit a certain amount of money to the supervised account.

  Grammar: 'having deposit of' INT


+ ##accumulative_view_event

  Use case: The resource was viewed upon accumulation of a certain amount of views.

  Grammar: 'per' INT 'views'

+ ##settlement_event

  pending
+ ##pricing_agreement_event
  pending

# Types
 + ## Enumerate
    + TIME_CYCLE

      pending

    + USER GROUP

       user_groups names are limited. There are only four types of user groups. AllVisiter, RegisteredUser, LoginUser, RegisteredNode.
  + ## Regular Expression
    + FEATHERACCOUNT

       FEATHERACCOUNT is account, it is either a 13-digit phone number or e-mail address.

       Regular Expression :[0-9a-zA-Z@.]+;
    + INT

       INT is non-negative integer.

    + ID

        ID are symbols that includes Upper Case, lower case or underscore.

        Regular Expression :([a-zA-Z]|'_')+;


# Reserved words
  * for: followed by user group, node group, domain name, or system gruop

  * initial: a initial state of a smart contract, every contract starts with state **initial **

  * proceed to: followed by a state name

  * on: followed by an event name

  * AllVisiter: target users are all users.

  * LoginUser: target users are visitors who have registered on www.freelog.com

  * Node: target users are users who have registered on www.freelog.com
