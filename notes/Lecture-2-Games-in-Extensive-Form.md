# Lecture 2 — Games in Extensive Form

*PPHA 41501 Game Theory (PhD), Autumn 2026 — Konstantin Sonin*
*Source deck: `slides/Lecture-Slide-2-Games-in-Extensive-Form.pdf` (40 slides, taught Thu 10/1)*

## Where the lecture is going (slide 2)

Four stops. Games in extensive form; information sets and the remaining
formalities; the relationship between the normal and the extensive form of the
same game; and imperfect information. The lecture is built so that the formal
apparatus arrives only after three examples have made it feel necessary.

## Motivating trees: chess, draughts, Hex (slides 3–6)

Chess opens the lecture as the paradigm case of a game where the players move in
turn and each sees what the other has done. The slide shows only the board. The
next slide draws what the board really is, a tree: each node is a position, each
edge a legal move, and play descends from a single root. Chess is the reason the
course needs a second representation at all, since a strategic-form matrix cannot
represent a game in which the second player's information changes as the first
player moves.

Draughts is offered as the same shape with a smaller board. **Hex** is the more
interesting case. In Hex a move can never be wasted and **no draw is possible**,
so every completed game has a winner. Both facts are stated on the slide, and the
class is asked to prove the consequence: **the first mover has a winning
strategy**. The proof is the classical strategy-stealing argument, and the slide
points to a playable board at https://playhex.org/. Hex is worth remembering
because it is a game whose first-mover advantage is provable without exhibiting
the strategy.

## The smallest extensive-form game (slides 7–9)

The deck's first explicit example strips the tree to its bones. Two players.
Player 1 chooses **up** or **down**. Then player 2 chooses **left** or **right**.
Player 2's choice is made after observing player 1's, and the slide draws both of
player 2's decision nodes separately, one under "up" and one under "down". This
is what distinguishes the extensive form from a matrix: the same nominal move by
player 2 appears twice, at two different nodes.

Slide 8 names the picture, "The Extensive Form", and slide 9 adds the **payoffs
notation**. Payoffs are attached to the terminal nodes only, and each terminal
node carries a vector, one number per player, written $(u_1, u_2)$. Nothing is
attached to interior nodes.

## Payoffs and the fight example (slides 10–11)

**Example, the decision to fight (slide 10).** Two players, an Incumbent and a
Challenger. First the Challenger decides whether or not to challenge. Second the
Incumbent decides whether or not to fight. The preferences are given in words.

- The Challenger prefers to enter, but not to fight.
- The Incumbent prefers that there is no challenge.
- If there is a challenge, the Incumbent prefers not to fight.

Slide 11 draws the tree. The Challenger's two branches are $In$ and $Out$, and
under $In$ the Incumbent chooses between $Acquiesce$ and $Fight$. The slide
labels the terminal payoffs $(1,2)$, $(0,\dots)$, so the reader can see the
Incumbent's preferred outcome sitting at the node the Challenger would rather
avoid creating. This example returns twice later in the lecture, once as a
strategy-counting exercise and once to show why the missing element matters.

## Ordinal versus cardinal, revisited (slide 12)

The slide restates the point from Lecture 1 in the new setting. For decisions,
what matters is whether one outcome is better than another, and not by how much.
The numbers in a tree are therefore labels for an ordering, not quantities to be
added. In the Cold War example that follows, the numbers are Sonin's own
calibration rather than Schelling's.

## Schelling's Cold War (slides 13–16)

The source is Thomas Schelling, *Arms and Influence* (1966), with the numbers
supplied by the instructor. The players are the United States and the Soviet
Union. The United States moves first: **use tanks in Berlin** or **do not use
tanks**. The Soviet Union then chooses whether to launch a nuclear attack, and
the structure of the tree gives the Soviet Union a decision at more than one
place, which is what makes it a game of consequence rather than a single choice.

The strategic-form version shown on slides 15 and 16 puts the United States in
the rows and four Soviet strategies in the columns, ordered as (nuclear attack,
nuclear attack), (nuclear attack, no attack), (no attack, nuclear attack), (no
attack, no attack).

$$\begin{pmatrix} (-10,-5) & (-10,-5) & (2,-3) & (2,-3) \\ (-9,-2) & (1,1) & (-9,-2) & (1,1) \end{pmatrix}$$

The top row is "use tanks", the bottom row is "do not use tanks". The slide is
explicit that these numbers are the instructor's, not Schelling's.

Slide 16 stays with the same game and shifts the frame of the argument, and
slides 15 and 16 are the two halves of the same discussion. The lecture closes
this thread with Khrushchev to the US Ambassador Averell Harriman.

> If you want war, you can have it, but remember it will be your war. Our
> rockets fly automatically.

The quotation is doing formal work. "Our rockets fly automatically" is an
attempt to remove the Soviet Union's own decision from the tree, and the lecture
uses it to show that the credibility of a threat depends on what the tree says
about who moves when.

## The formalities (slides 17–18)

Slide 17 lists what a game in extensive form requires.

- A game tree with nodes and edges connecting nodes.
- A function assigning a player to each node.
- Payoffs assigned to the terminal nodes.
- Information sets, flagged as "to be defined later".

The slide also says that a definition of a strategy for extensive-form games
comes next and that equilibrium waits until Lecture 4.

Slide 18 gives the tree itself precise content.

- A set of nodes $X$.
- A function mapping $X$ into the set of players $N$, assigning each node the
  player who acts there.
- A function assigning edges, that is actions $A(x)$, to each node $x \in X$. If
  $A(y) = \varnothing$, then $y$ is a **terminal node**.
- A payoff function $u$ mapping the set of terminal nodes into $\mathbb{R}^N$.
- The tree has one root and cannot have cycles: the same node cannot be reached
  by two different paths.
- Paths are called **histories**, and paths that end at terminal nodes are
  **terminal histories**. The set of terminal histories includes infinite paths
  as well.

## Strategies in an extensive-form game (slides 19–23)

This is the conceptual hinge of the lecture. A **strategy of player $i$** is a
function that assigns an action to **every node where it is $i$'s turn to move**,
not merely to the nodes that the eventual play happens to visit. The slide puts
the contrast plainly: unlike in games in normal form, in extensive-form games
there is a difference between a strategy and an action.

The consequence stated on the slide is that once each player has decided on a
strategy, the game can be played by an automaton from any node. The definition is
therefore a complete contingency plan, which is why the slide calls a strategy in
an extensive-form game "a battlefield plan". Given a strategy profile there is a
history corresponding to that profile, the game path, and the payoffs attached
to that path are the payoffs of the profile.

Slides 20 and 21 apply the definition to the first example. The questions are how
many strategies each player has, and the answers are:

- Player 1 has two strategies, $\{U, D\}$.
- Player 2 has four strategies, $\{(L,l), (L,r), (R,l), (R,r)\}$.

The count for player 2 is the whole point. Player 2 is asked to specify a choice
at both of his nodes, including the node that will not be reached, so his
strategy set has $2 \times 2 = 4$ elements and the game has $2 \times 4 = 8$
strategy profiles.

Slides 22 and 23 repeat the count for the two running examples.

- Entry example. Challenger: $\{In, Out\}$. Incumbent: $\{Acquiesce, Fight\}$.
- Cold War example. United States: $\{Use tanks, Do not use tanks\}$. Soviet
  Union: $\{No attack, nuclear attack\}$, $\{No attack, no attack\}$,
  $\{Nuclear attack, nuclear attack\}$, $\{Nuclear attack, no attack\}$.

## Back to the strategic form (slides 24–27)

Slide 24 asks what happens if the Cold War game, introduced as a tree, is written
as a strategic-form game. Slides 25 through 27 then run three comparisons, each
of which is a warning.

**The prisoner's dilemma (slides 25–26).** The matrix is the familiar one, with
Suspect 1 in the rows and Suspect 2 in the columns, where "don't confess" against
"don't confess" gives $(-1,-1)$, either one confessing alone gives $(-10, 0)$ or
$(0, -10)$, and mutual confession gives $(-8, -8)$. The question is whether the
prisoner's dilemma is a prisoner's dilemma **in extensive form**, and the slide
answers: in fact, no, though the outcome is the same. The reason is visible in
the strategy lists, since Suspect 2's strategies are
$\{Don't\ confess, Don't\ confess\}$, $\{Confess, Don't\ confess\}$,
$\{Don't\ confess, Confess\}$ and $\{Confess, Confess\}$. Writing a game in a
tree adds structure that the matrix does not have, and the tree can change what
the game is.

**The entry game (slide 27).** The matrix has Candidate 1 in the rows and
Candidate 2 in the columns, with $(-1,-1)$, $(1,0)$, $(0,1)$ and $(0,0)$. The
slide asks what the outcome is and whether it is the same game, and answers
**NO**. Sequential entry and simultaneous entry are different games even when
the payoff table is identical.

## Information sets, the missing element (slides 28–29)

Slide 28 names what was missing from the formal list on slide 17. To define a
strategic game in extensive form one needs the tree, the player function, the
terminal payoffs, and **information sets**.

Slide 29 then redraws the entry game with the information sets attached and
reports that the game is now equivalent to the entry game discussed in normal
form. Player 1 chooses between $\{Enter, Do not\ enter\}$ and player 2 chooses
between $\{Enter, Do not\ enter\}$. The lesson is that the tree alone does not
determine the game. Whether player 2's two decision nodes sit in one information
set or in two is the substantive modelling decision, and it is exactly the
decision that distinguishes the games of slides 27 and 29.

## Rock, paper, scissors as a tree (slides 30–32)

Rock, paper, scissors is the cleanest illustration of the opposite direction.
Written in normal form it is the familiar three-by-three table, with $0, 0$ on
the diagonal, and the off-diagonal cells equal to $0, 1$ or $1, 0$.

$$\begin{pmatrix} (0,0) & (0,1) & (1,0) \\ (1,0) & (0,0) & (0,1) \\ (0,1) & (1,0) & (0,0) \end{pmatrix}$$

Slide 32 writes the same game as an extensive form. Player 1 moves first and
player 2 moves second, but player 2's nodes are gathered into a single
information set, so player 2 cannot condition on player 1's choice. The tree is
drawn with three branches at the root and three at each of player 2's nodes, and
the payoffs at the leaves reproduce the matrix. This is the lecture's clearest
statement that simultaneity is a statement about information sets rather than
about clocks.

## Full formalities and general equivalence (slides 33–34)

Slide 33 gives the definitive list.

- A set of nodes $X$.
- A partition of $X$ into information sets.
- A function determining the player who acts in each information set.
- A function assigning edges to each information set, with the requirement that
  all nodes in an information set have the same outgoing edges.
- A payoff function mapping the terminal nodes, that is histories, into
  $\mathbb{R}^N$.
- A strategy of player $i$ is a function that assigns an action to every
  information set where it is $i$'s turn to act.

Slide 34 states the general equivalence. Every game in extensive form can be
represented in an equivalent strategic form and vice versa, but the slide adds
the warning to be careful, and then the reason the warning matters: the choice of
modelling approach is dictated by the research question and the researcher's
approach, since it may be reasonable to assume that some moves are naturally
simultaneous while others are sequential. Equivalence of the representations does
not mean indifference between them.

## The simple card game, Myerson 2.1 (slides 35–40)

The lecture ends with the card game from Myerson, numbered 2.1 in the notes.

- Players 1 and 2 each put $1 in the pot.
- Player 1 draws a card from the deck and looks at it privately.
- Player 1 decides whether to Fold or Raise.
- If player 1 folds, the card is shown to player 2 and the game ends. If the card
  is red, meaning diamonds or hearts, player 1 wins the pot; if it is black,
  clubs or spades, player 2 wins.
- If player 1 raises, she adds another $1 to the pot.
- Player 2 then decides whether to Meet or Pass. If player 2 passes, player 1
  wins the pot. If player 2 meets, he adds another $1, the card is shown, and the
  game ends with the same colour rule deciding the pot.

Slide 36 introduces the device that lets a deterministic tree carry randomness:
a **chance node** labelled "0", or "Nature". The slide notes that the game may
become one with imperfect information, because player 2 does not observe the
card. Slides 37 and 38 draw two candidate trees for the card game and ask which
one is right, which is the information-set question again in a sharper form: the
two trees differ in what player 2 knows when he moves.

Slide 39 counts the strategies:

- Player 1: $\{Rr, Rf, Fr, Ff\}$, that is raise-or-fold paired with what she does
  on red and on black.
- Player 2: $\{M, P\}$.

Slide 40 puts the game in strategic form and shows one payoff calculation in
full, for the profile (raise, fold) against meet:

$$u_1(Rf, M) = \tfrac{1}{2} \times 2 + \tfrac{1}{2} \times (-1) = \tfrac{1}{2}$$

$$u_2(Rf, M) = \tfrac{1}{2} \times (-2) + \tfrac{1}{2} \times 1 = -\tfrac{1}{2}$$

The half is the probability of a red card, and the two terms are the red and
black branches. The full matrix has player 1 in the rows.

$$\begin{pmatrix} (0,0) & (1,-1) \\ (\tfrac{1}{2},-\tfrac{1}{2}) & (0,0) \\ (-\tfrac{1}{2},\tfrac{1}{2}) & (1,-1) \\ (0,0) & (0,0) \end{pmatrix}$$

The rows are (raise, raise), (raise, fold), (fold, raise) and (fold, fold), and
the columns are meet and pass.

## Difficulty checklist

1. **Strategy is not action.** In an extensive-form game a strategy assigns an
   action to every node where the player moves, including nodes that play will
   never reach. Player 2 in the two-move example has four strategies, not two
   (slides 19–21).
2. **The tree can change the game.** The same payoff table yields different games
   under sequential and simultaneous play; slide 27 answers "NO" to whether the
   extensive and normal forms of the entry game are the same (slides 25–27).
3. **Information sets are the real modelling choice.** Rock, paper, scissors is
   simultaneous precisely because player 2's nodes share one information set;
   the entry game becomes the normal-form game only once its nodes are grouped
   the same way (slides 29–32).
4. **Payoffs live at terminal nodes.** Interior nodes carry a player, not a
   payoff, and each terminal node carries a vector $(u_1, u_2)$ (slides 8–9).
5. **One root, no cycles.** The same node cannot be reached by two different
   paths, and the set of terminal histories includes infinite paths (slide 18).
6. **Ordinal, not cardinal.** The numbers in the Cold War tree are the
   instructor's calibration, and what the theory needs from them is only the
   ordering (slides 12–13).
7. **Equivalence is not indifference.** Every extensive-form game has a strategic
   form and vice versa, but the slide warns to be careful, and the choice of
   representation follows the research question (slide 34).
8. **Chance is a player-like node.** Randomness enters the tree as Nature, node
   0, which is also what makes imperfect information possible in the card game
   (slides 36–38).
9. **Hex has no draws.** The first mover's winning strategy exists; the slide
   asks for the proof rather than for the strategy (slide 6).
10. **The deliverable for this lecture is the language, not the solution
    concept.** Equilibrium arrives in Lecture 4, and the card game is left as a
    matrix without a solution concept attached (slides 17, 40).
