# Ballot sender
A Utility for sending out ballots to the members of Coding Pirates.

## Use case
When the Board of Coding Pirates wants the union to vote on a proposal we must
send out ballots to all our members. We use [opavote](https://www.opavote.com),
to handle the voting.

OpaVote does not supports our needs, since we send the ballots to the family
mail which might include multiple members we need to send more than one ballot
to some mails accounts.

Opavote supports generating _vote codes_ which is a small string that can be
entered to cast a vote.

The goal of this piece of software is to take a csv file with the following
format.

| Name  | Person email   | Family email    | Ballot code |
|-------|----------------|-----------------|-------------|
| Alice | alice@mail.com | family@mail.com | xxx         |
| Bob   |                | family@mail.com | xxx         |
| ...   | ...            | ...             | xxx         |

And send an email to every person with a ballot code and if the family mail is
different an email with all the ballot codes for that family.

## Technical setup and
The code is written in haskell and executed in a docker container.

