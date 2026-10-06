# Lecture 1 — Games in Strategic Form

*PPHA 41501 Game Theory (PhD), Autumn 2026 — Konstantin Sonin*
*Source deck: `slides/Lecture-Slide-1-Games-in-Strategic-Form.pdf` (44 slides, taught Tue 9/29)*

## Administrative frame (slides 2–11)

The opening block sets the rules of the course. Slides 2–4 give the plan of the
first meeting (house-keeping, course outline, then strategic-form games), the
instructors, and where materials live. Instructor Konstantin Sonin
(ksonin@uchicago.edu, office Keller 2021), with office hours after lectures or by
appointment. TAs Kenneth Cowles (kcowles@uchicago.edu) and Grace Leo
(gleo@uchicago.edu). Slides and other materials are on Canvas; textbooks contain
the lecture material and more; there will be occasional articles for discussion;
video recordings are posted whenever possible.

Slide 5 lists the textbooks. Everything needed is on the slides, but the best
reference is Myerson, *Game Theory: Analysis of Conflict*. Introductory
alternatives are Gibbons, *A Primer in Game Theory* and Osborne, *An Introduction
to Game Theory*. More advanced: Osborne and Rubinstein, *A Course in Game
Theory*; Fudenberg and Tirole, *Game Theory*; and Mas-Colell, Whinston and Green,
*Microeconomic Theory* (chapters 5–8).

Slide 6 is a note on AI. The course's premise is that in 2026 AI has surpassed
human ability at mathematics, so "solving" games has become routine for AI. The
implications fall on assignments and grading, and on the learning process; a
class ChatBot (Claude Enterprise) has been created, subject to University of
Chicago and Harris policy.

Slide 7 gives the grade components: class participation, home assignments, a
small take-home midterm, in-class quizzes, and the final exam. Live attendance is
expected; students who need to learn remotely must contact Dean of Students Kate
Biddle (kbiddle@uchicago.edu).

Slide 8 covers problem sets: three of them, each with an ungraded part (itself
split into an obligatory part, "as obligatory as the graded part", and a
non-obligatory part) and a graded part scored from 1 to 100+. Work may be
discussed with others but must be handed in individually, and late homework takes
a heavy discount. Slide 9 describes TA sessions as a solitary learning exercise:
an hour, a sequence of problems, no help, ungraded, with a reward based on where
the student stops.

Slides 10 and 11 set expectations. Students should be familiar with basic
probability, and the class has substantial heterogeneity. The pace starts slow
because the first examples matter. Three caveats: textbooks differ in
definitions, concepts and approaches; textbooks differ (marginally) in
terminology; and the same object may be labelled differently across sources.

## What game theory is (slides 12–14)

Slide 12 defines game theory as a mathematical theory for strategic analysis,
applied in political science, economics, the analysis of conflict, biology, and
transportation. Slides 13 and 14 give the sources of its examples. In economics:
markets with few big players; market interactions such as bilateral trade (two
strategic parties haggling over a price) and auctions (a sale whose price is
determined during the sale); and intra-firm relationships such as
principal–agent problems. In political science: electoral politics (interaction
between candidates), parliamentary politics (interaction between members of
parliament and agenda-setting), international relations (arms races, strategic
alliances), and nondemocratic politics (dictators and protesters).

## Course roadmap (slides 15–16)

The two roadmap slides list the eighteen lectures in order: (1) games in
strategic form; (2) games in extensive form; (3) Nash equilibrium; (4) Nash
equilibrium in extensive-form games; (5) Nash equilibrium examples, a model of
political competition; (6) Nash equilibrium examples, committee
decision-making; (7) the Nash existence theorem; (8) games of imperfect
information; (9) signaling games; (10) Bayesian persuasion; (11) repeated games;
(12) the folk theorem; (13) Markov games and Markov perfect equilibrium;
(14) bargaining and coalition formation; (15) cooperative games; (16) matching;
(17) social choice and mechanism design; (18) auctions.

## Three basic elements and two assumptions (slides 17–19)

Slide 17 names the primitives. A **game** is any interaction between players
(people, organizations, countries) in which strategic behavior plays a major
role. **Players** are the participants. **Strategies** are "battlefield plans"
that specify the actions a player will take. **Payoffs** are players' valuations
of the outcome. A player's only interest in the game is to maximize [expected]
payoffs.

Slide 18 states the two major assumptions. Players maximize payoffs, and under
uncertainty they maximize **expected** payoffs. All players share **common
knowledge** about how the game is played. Slide 19 fixes the information
vocabulary used in the course: common knowledge is always assumed; **perfect
(complete) information** means players know other players' moves and payoffs;
**imperfect (incomplete) information** means they do not know something about
those moves and payoffs.

## Strategic-form games: definition and formalism (slides 20–23)

Slide 20 notes that one game admits several representations, then defines the
**strategic (normal) form**: a representation of a game with complete information
that specifies the players, their possible strategies, and payoff functions
giving each player's payoff for every combination of strategies. In such a game
players move simultaneously; "dynamic" games, in which players move sequentially
or repeatedly, come later.

Slide 21 formalizes this. A full description requires a set of players $N$, for
each player $i \in N$ a set of strategies $S_i$, and for each player $i \in N$ a
mapping from strategy profiles to real payoffs:

$$G = \langle N, \{S_i\}_{i \in N}, \{u_i\}_{i \in N} \rangle, \qquad u_i : S_1 \times \cdots \times S_N \to \mathbb{R}$$

An element of $S_1 \times \cdots \times S_N$ is called a **strategy profile**.

Slides 22 and 23 specialize to two-player, two-strategy games, the **2×2 games**
that supply most examples. Player 1 has $S_1 = \{U, D\}$ and Player 2 has
$S_2 = \{L, R\}$; the payoffs are $u_1(U,L)$, $u_1(U,R)$, $u_1(D,L)$, $u_1(D,R)$
for Player 1 and the four matching values for Player 2. The matrix representation
puts Player 1's strategies on the rows and Player 2's on the columns, with each
cell carrying the ordered pair $(u_1, u_2)$:

$$\begin{pmatrix} (u_1(U,L),\, u_2(U,L)) & (u_1(U,R),\, u_2(U,R)) \\ (u_1(D,L),\, u_2(D,L)) & (u_1(D,R),\, u_2(D,R)) \end{pmatrix}$$

## The airline example (slides 24–26)

Slides 24–26 build a running example. Two airlines, American and United, each
choose a quarterly capacity between Chicago and Los Angeles: fly 40,000
passengers or fly 60,000. Two assumptions pin down the profit structure: the more
passengers served, the lower the profit per passenger, and profits are divided
proportionally.

The payoffs follow. If the two firms act as a monopoly and fly
$40{,}000 + 40{,}000 = 80{,}000$ passengers, joint profit is 40 million dollars
per quarter, so each earns 20 million dollars. If American flies 60,000 and
United flies 40,000, American earns 21 million dollars and United 14 million
dollars; the mirror outcome swaps the two. If both fly 60,000, each earns 15
million dollars. The matrix, in millions of dollars, is

$$\begin{pmatrix} (20, 20) & (14, 21) \\ (21, 14) & (15, 15) \end{pmatrix}$$

with rows American (40,000 then 60,000) and columns United (40,000 then 60,000).

## Arms race and the prisoner's dilemma (slides 27–29)

Slide 27 recasts the same logic as an arms race between the United States and the
Soviet Union, with actions "don't build bombs" and "build bombs":

$$\begin{pmatrix} (2,2) & (0,3) \\ (3,0) & (1,1) \end{pmatrix}$$

Slide 28 gives the **prisoner's dilemma**, two suspects choosing whether to
confess:

$$\begin{pmatrix} (-1,-1) & (-10,0) \\ (0,-10) & (-8,-8) \end{pmatrix}$$

Slide 29 defines the dilemma: a game in which all players optimally choose
strategies that deliver payoffs inferior to what coordination on the jointly
better action (here, not confessing) would have achieved.

## Ordinal versus cardinal utility (slide 30)

Slide 30 observes that the airline, arms-race and prisoner's-dilemma games are
"essentially the same game": each player's choice depends on relative, not
absolute, payoffs. Such payoff functions are **ordinal** and carry no information
about magnitude or intensity of preference. **Cardinal** payoff functions do
communicate intensity. Game theory is mostly about ordinal utility functions.

## A simple entry game (slides 31–32)

Slides 31–32 introduce two politicians considering entry into a primary who would
rather not run against each other:

$$\begin{pmatrix} (-1,-1) & (1,0) \\ (0,1) & (0,0) \end{pmatrix}$$

Rows are Candidate 1 (Enter, Don't enter) and columns Candidate 2.

## Coordination games (slides 33–35)

Slide 33 presents a streaming-services coordination problem. Amazon and Disney+
each choose a genre for the next season, Space Travel or Medieval Age Fantasy;
Disney+'s alternatives are labelled "Hobbit+" and "Star Wars+":

$$\begin{pmatrix} (100,-100) & (500,300) \\ (200,250) & (50,100) \end{pmatrix}$$

Slide 34 gives **Bach or Stravinsky** (formerly "Battle of the Sexes"): two
friends want to be together but prefer different concerts,

$$\begin{pmatrix} (2,1) & (0,0) \\ (0,0) & (1,2) \end{pmatrix}$$

Slide 35 gives the **stag hunt**: two hunters, a stag that one hunter cannot
catch alone, and the option of a hare each,

$$\begin{pmatrix} (2,2) & (0,1) \\ (1,0) & (1,1) \end{pmatrix}$$

## The regulation game and zero-sum games (slides 36–39)

Slides 36–37 give a game of regulation, the political-economy example closest to
the course's applications. A firm chooses where to pollute and a regulator
chooses which one site to check; the firm profits if it is not caught, and the
regulator is rewarded if it catches pollution. The payoff matrix is the
anti-coordination structure of matching pennies:

$$\begin{pmatrix} (0,1) & (1,0) \\ (1,0) & (0,1) \end{pmatrix}$$

Slide 38 names this game **matching pennies** and **zero-sum**: two players
simultaneously show heads or tails; matching sides means Player 1 pays Player 2 a
dollar, and non-matching sides reverse the payment,

$$\begin{pmatrix} (-1,1) & (1,-1) \\ (1,-1) & (-1,1) \end{pmatrix}$$

Slide 39 generalizes: a game is **zero-sum** when one player's win is the other's
loss, written with a generic payoff matrix

$$\begin{pmatrix} (a,-a) & (c,-c) \\ (b,-b) & (d,-d) \end{pmatrix}$$

## A common metaphor (slides 40–42)

Slides 40 and 41 are the visual metaphor for the zero-sum idea (the deck carries
two images, with the second captioned "Not necessarily Trump"). Slide 42 draws
the conceptual distinction. **War** is often zero-sum, since one side's loss is
the other's win. **Trade** is mostly a prisoner's-dilemma-type game, because one
outcome is mutually preferred to another. The slide closes with two open
questions: can you think of a war that is a prisoner's-dilemma-type game, and can
you think of a trade that is zero-sum?

## Nim, before the next lecture (slide 43)

Slide 43 sets a puzzle to work before Lecture 2. There are $n$ piles of stones of
sizes $k_1, \dots, k_n$. Two players alternate moves; a move removes one or more
stones (up to all) from a chosen pile; the player who takes the last stone wins.
The questions are how to win when $n = 2$ and when $n > 2$, and which player wins
in each case, the first mover or the second.

## A very brief history (slide 44)

The closing slide is a timeline of the field. 1713, Waldegrave, the first
strategic analysis. 1838, Cournot, the prototype of Nash equilibrium. 1928 von
Neumann on two-player zero-sum games, and 1944 von Neumann and Morgenstern,
*Game Theory and Strategic Behavior*. 1950 Nash on equilibrium and cooperative
games, alongside RAND, Shapley and Shubik on the analysis of conflict. The 1960s
add Aumann, Harsanyi and Selten on mathematical foundations, and 1960 Schelling's
*Strategy of Conflict* (highly recommended). The 1970s add Maskin, Myerson and
Holmström on mechanism design and auctions; the 1980s Milgrom, Roth and Wilson on
market design. The 1994 Nobel went to Nash, Selten and Harsanyi (with the Nash
biography *A Beautiful Mind* recommended). 2002 brought the Academy Awards for the
film. Further Nobels for game theory came in 2005, 2007, 2012, 2014 and 2020,
with the Nobel lectures recommended.

## Difficulty checklist

1. **Strategic form is simultaneous by construction.** The normal form encodes
   players moving at once; sequential and repeated play is deliberately deferred
   to the extensive form (slides 20, 15–16).
2. **Payoff functions are ordinal, not cardinal.** The airline, arms-race and
   prisoner's-dilemma matrices are the same game once relative rankings are what
   matter (slide 30); do not import intensity from the numbers.
3. **The matrix convention.** Rows are Player 1's strategies, columns Player 2's,
   and each cell holds the ordered pair $(u_1, u_2)$; mixing up the order silently
   reverses every preference comparison (slides 22–23).
4. **Perfect versus imperfect information.** "Complete information" is about
   knowing moves and payoffs, not about the timing of moves; the two axes are
   distinct (slide 19).
5. **Common knowledge is assumed throughout.** The course does not relax it in
   these first lectures (slides 18–19).
6. **Zero-sum is a payoff condition, not a game name.** Matching pennies happens
   to be zero-sum, and the anti-coordination structure recurs in the regulation
   game; zero-sum is defined by $u_2 = -u_1$ (slides 37–39).
7. **One interaction, several games.** War reads as zero-sum and trade as
   prisoner's-dilemma in the standard telling, but the slide asks for
   counterexamples, so treat the mapping as a default rather than a theorem
   (slide 42).
8. **Problem sets are structured but individual.** Each has three obligatory
   parts plus one for those who find the material easy, only one part is handed
   in, and formulae-processing software is mandatory, with heavy discounts for
   lateness (slides 8, and syllabus).
9. **TA sessions are ungraded but rewarded.** The prize scales with how far the
   student gets, so pace and completeness both matter (slide 9).
10. **The pace is deliberately slow at the start.** The first examples carry the
    conceptual load, and the deck flags substantial heterogeneity across students
    (slides 10–11).
