## Governance

### Charter

All dynamic aspects of the X7 ecosystem will ultimately rest with the DAO to decide upon.

The DAO will be responsible for modifying tokenomics, changing profit allocation, upgrading the upgradeable components, and determining the long-term fate of locked liquidity.

The **X7DAO** token is the voting token within the DAO,and a portion of project revenue will flow into the DAO token in the form of liquidity injections.

The expected outcome is that DAO holders will maximize the medium and long-term gain of the DAO token. The ecosystem properly aligns this selfish profit motive with the efficient and healthy operation of the ecosystem.

### Control Structure

The DAO shall operate through central governance contracts. For all functions the DAO may control, there will be two options:

1. Make the relevant change
1. Delegate the authority to make those kinds of changes to an address.

The expected way that this will work is that multi-signature wallets will be deployed to form “committees” which can self-govern in terms of membership in the committee and the operations the committee executes.

At any time a DAO vote can be undertaken to revoke authority from a committee if it is not performing as needed

For example, one feature that will exist is the addition of new loan term contracts. In order to efficiently respond to the market, the DAO could vote to allow a developer or a multi-signature wallet controlled by a number of known parties the ability to add and remove loan term contracts. This group could also be funded by the treasury to pay for the development and audits of new loan term contracts. This group could do market research and rapidly iterate to find profit-maximizing terms. If this group begins to operate maliciously or ineffectively, their control of the loan term change capability can be revoked.

### DAO configuration

The core quorum and proposal thresholds are not configurable.

However, it is not known a-priori how rapid voting phases should be. There is a tradeoff between speed of execution and time for deliberation that must be balanced. The initial durations for each proposal phase will be set as a starting point. However, these durations may be changed (within hard-coded limits) to meet future governance needs.

### Proposals and Voting

Voting will occur in multiple phases, each of which has either a minimum or maximum time phase duration.

#### Phase 1: Quorum-seeking

**X7DAO** token holders will be able to stake their tokens as X7sDAO, a non-transferrable staked version of **X7DAO**.

A quorum is reached when more than 50% of circulating **X7DAO** has been staked as X7sDAO.

Once a quorum is reached and a minimum quorum-seeking time period has passed, the

X7sDAO tokens are temporarily locked (and no more **X7DAO** tokens may be staked until the next Quorum seeking period) and the governance process moves to the next phase

#### Phase 2: Proposal creation

A proposal is created by running a transaction on the governance contract which specifies a specific transaction on a specific contract (e.g. setFeeNumerator(0) on the **X7R** token contract).

Proposals are ordered, and any proposals that are passed/adopted must be run in the order that they were created.

For example, if there were two proposals, the first to setFeeNumerator(0) and the second to setFeeNumerator(500), that both passed, the first setFeeNumerator(0) would be run, and then setFeeNumerator(500) would be run, resulting in the feeNumerator being 500. This can be used strategically by proposers to create “nullifying” proposals to maximize the time they have to advocate for their position of non-action in the event the original change should pass.

Proposals can be made by X7sDAO stakes of 500,000 tokens or more. Additionally, holders of Magister tokens may make proposals. Proposals may require a refundable proposal fee to prevent process griefing.

#### Phase 3: Proposal voting

Each proposal may be voted on once by each address. The voter may specify the weight of their vote between 0 and the total amount of X7sDAO they have staked.

Proposals pass by a majority vote of the quorum of X7sDAO tokens.

A parallel voting process will occur with Magister tokens, where each Magister token carries one vote.

If a majority of magister token holders vote against a proposal, the proposal must reach an X7sDAO vote of 75% of the quorum of X7sDAO tokens.

#### Phase 4: Proposal adoption

During this phase, proposals that have passed will be enqueued for execution. This step ensures proper ordering and is a guard against various forms of process griefing.

#### Phase 5: Proposal execution

After proposal adoption, all passed proposals must be executed before a new Quorum Seeking phase may commence.

#### Process Adaptation

Since any change that the core DAO governance process can control may be delegated, novel other mechanisms for voting may be created and changes can be delegated to that new process.

For example, a trusted group of individuals could be delegated control, and that trusted group could run an off-chain trustful process of voting.

If this process was ever corrupted, the DAO could regain trustless on-chain control through a majority vote.

The X7 developers believe this governance structure will enable novel future governance innovation while never permanently relinquishing control to any external authority.

#### Tokenized Governance

The X7 DAO structure is highly codified and provides almost no direct latitude for human intervention. This is by design and is one of the greatest strengths of the X7 DAO governance structure.

There is however a chance that through collusion and the inaction of DAO holders a large DAO holder could submit a proposal that was in their best interest and and not the best interest of the project.

To help provide a check and balance, a maximum of 49 Magister tokens can be minted. Seven of these tokens were minted and given to the X7 development team. The other 42 may be minted for a fee.

Any proposal may be vetoed by a majority of minted Magister tokens. It will require a ¾ supermajority DAO vote to overturn a Magister veto.

An additional side effect of this governance feature is that the original ecosystem developers will retain a level of authority at the beginning of DAO control handover, but this authority can and will be diluted as Magister tokens are minted. The final governance influence of the original developers will become minimal once all Magister tokens have been minted, and once 8 additional Magister tokens are minted the original developers will no longer maintain a controlling voting block on Magister votes.
