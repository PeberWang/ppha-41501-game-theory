# Lecture 3 — Nash Equilibrium

*PPHA 41501 Game Theory (PhD), Autumn 2026 — Konstantin Sonin*
*Source deck: `slides/Lecture-Slide-3-Nash-Equilibrium.pdf` (40 slides, taught Tue 10/6)*

<!-- Page 1 -->

## Plan (slide 2)

<!-- Page 2 -->

Four stops: best responses; Nash equilibrium; mixed strategies; weak and strong
domination. The lecture builds the solution concept out of the best-response idea
introduced informally in Lecture 1, first for pure strategies — the "strategies"
of the earlier lectures — and then for mixtures.

<!-- Page 3 -->

## Three different cases (slide 3)

The lecture opens with three matrices that motivate everything after it, because
the theory of Nash equilibrium has to say something in each case.

The arms-race game (the United States and the Soviet Union, each choosing whether
to build bombs) is the case of **one plausible outcome**:

$$\begin{pmatrix} (2,2) & (0,3) \\ (3,0) & (1,1) \end{pmatrix}$$

The entry game (two candidates deciding whether to enter a primary) is the case of
**two plausible outcomes**:

$$\begin{pmatrix} (-1,-1) & (1,0) \\ (0,1) & (0,0) \end{pmatrix}$$

The regulation game (a firm choosing where to pollute, a regulator choosing which
site to check) is the case of **no plausible outcome** in pure strategies:

$$\begin{pmatrix} (0,1) & (1,0) \\ (1,0) & (0,1) \end{pmatrix}$$

The first two are resolved by the pure-strategy concept; the third is what forces
mixed strategies into the theory.

<!-- Page 4 -->

## Best response and Nash equilibrium: the definitions (slide 4)

**Best response** is a strategy that maximizes a player's payoff given that
player's assumption about the rival's strategy: fix the rivals' strategies, then
look at the best responses to them. **Nash equilibrium** is a set of strategies
such that, when all other players use these strategies, no player can obtain a
higher payoff by choosing a different strategy.

<!-- Page 5 -->

## Best responses in the arms race and the entry game (slides 5–6)

In the **arms race**, each player's best reply is to build regardless of what the
other does. Writing $b_{US}(s_{SU})$ for the US's best reply to each Soviet
strategy $s_{SU}$ and $b_{SU}(s_{US})$ for the Soviet Union's best reply to each
US strategy,

$$b_{US}(\text{Don't build}) = \text{Build}, \quad b_{US}(\text{Build}) = \text{Build}, \quad b_{SU}(\text{Don't build}) = \text{Build}, \quad b_{SU}(\text{Build}) = \text{Build}.$$

<!-- Page 6 -->

In the **entry game** the two players' preferences run opposite, and the slide
states them in words:

- If Candidate 1 enters, Candidate 2 prefers not to enter.
- If Candidate 1 does not enter, Candidate 2 prefers to enter.
- If Candidate 2 enters, Candidate 1 prefers not to enter.
- If Candidate 2 does not enter, Candidate 1 prefers to enter.

Written as best replies,

$$b_1(\text{Enter}) = \text{Don't enter}, \quad b_1(\text{Don't enter}) = \text{Enter}, \quad b_2(\text{Enter}) = \text{Don't enter}, \quad b_2(\text{Don't enter}) = \text{Enter}.$$

Each player's best response is to do the opposite of the rival.

<!-- Page 7 -->

## Best response, formally (slide 7)

A strategic-form game is a set of players $N$, for each player $i \in N$ a set of
strategies $S_i$, and for each player a payoff mapping

$$G = \langle N, \{S_i\}_{i \in N}, \{u_i\}_{i \in N} \rangle, \qquad u_i : S_1 \times \cdots \times S_N \to \mathbb{R}.$$

Fix a strategy for every player except $i$, the profile
$s_{-i} = (s_1, s_2, \ldots, s_{i-1}, s_{i+1}, \ldots, s_N)$. A strategy
$s_i \in S_i$ is a **best response** to $s_{-i}$ if

$$u_i(s_i, s_{-i}) \ge u_i(t_i, s_{-i}) \quad \text{for any } t_i \in S_i.$$

The inequality is weak — "$\ge$", not "$>$" — and this is the detail that later
lets ties support whole sets of equilibria.

<!-- Page 8 -->

## A best-response exercise (slide 8)

The slide poses a seven-by-five strategic-form game (Player 1's strategies
$A$–$G$ in the rows, Player 2's $1$–$5$ in the columns) and asks for the best
responses:

$$\begin{pmatrix} (2,3) & (5,4) & (-8,1) & (-2,-3) & (0,1) \\ (8,-1) & (5,5) & (6,4) & (1,1) & (1,-12) \\ (1,3) & (-5,5) & (4,6) & (0,0) & (2,9) \\ (3,1) & (0,-1) & (3,7) & (8,-1) & (5,5) \\ (0,0) & (4,6) & (2,-3) & (1,3) & (-5,5) \\ (7,-2) & (3,3) & (5,-8) & (-11,1) & (-1,0) \\ (7,0) & (0,8) & (0,8) & (3,2) & (5,-7) \end{pmatrix}$$

The exercise is to read each player's best reply off the table: for each column,
the row that maximizes Player 1's payoff; for each row, the column that maximizes
Player 2's.

<!-- Page 9 -->

## Nash equilibrium (slide 9)

A strategy profile $(s_1^*, \ldots, s_N^*)$ is a **Nash equilibrium** of a
strategic-form game if for any player $i \in N$, $s_i^*$ is a best response to
$s_{-i}^*$:

$$u_i(s_i^*, s_{-i}^*) \ge u_i(t_i, s_{-i}^*) \quad \text{for all } t_i \in S_i \text{ and all } i \in N.$$

All equilibria found this way are Nash equilibria **in pure strategies**, and a
game may have other equilibria. The pure strategies of player $i \in N$ are all
the strategies in the set $S_i$ — before this lecture they were called simply
"strategies", and from here on the word has to be disambiguated from "mixed
strategy".

<!-- Page 10 -->

## John Nash (slide 10)

The slide is a portrait of John Nash, whose name the concept carries. In the
course's own timeline (Lecture 1) he is the 1950 contribution on equilibrium and
cooperative games, and the 1994 Nobel shared with Selten and Harsanyi.

<!-- Page 11 -->

## Nash equilibrium in the prisoner's dilemma (slide 11)

The prisoner's dilemma, with Suspect 1 in the rows and Suspect 2 in the columns:

$$\begin{pmatrix} (-1,-1) & (-10,0) \\ (0,-10) & (-8,-8) \end{pmatrix}$$

The unique Nash equilibrium is mutual confession, $(Confess, Confess)$, even
though mutual silence is jointly better. Each suspect's best reply to confession
is confession, so neither can gain by deviating.

<!-- Page 12 -->

## Nash equilibria in a coordination game (slide 12)

Amazon and Disney+ each choose a genre for the next season. The slide reads the
best responses in words:

- If Disney+ does a Star Wars, Amazon prefers to do a Hobbit.
- If Disney+ goes medieval, Amazon prefers a space saga.
- If Amazon does a Space Travel, Disney+ prefers a medieval epic.
- If Amazon does a Hobbit film, Disney+ chooses Yoda.

With Amazon's strategies (Space Travel, Medieval Age Fantasy) in the rows and
Disney+'s (Star Wars+, Hobbit+) in the columns,

$$\begin{pmatrix} (100,-100) & (500,300) \\ (200,250) & (50,100) \end{pmatrix}$$

and there are **two** Nash equilibria: (Space Travel, Hobbit+) and (Medieval Age
Fantasy, Star Wars+). The two outcomes are the same story told from opposite ends,
which is why the deck files the coordination game under two plausible outcomes.

<!-- Page 13 -->

## One equilibrium (slide 13)

The slide marks the middle case — a game with exactly one equilibrium. In the
deck's sequence it sits between the coordination game's two equilibria and the
catalogue of three counts on the next slide, as the visual reminder that a single
equilibrium is possible.

<!-- Page 14 -->

## Three examples: two, one, none (slide 14)

The slide collects the three counts against three games.

**Two Nash equilibria in pure strategies** — the stag hunt:

$$\begin{pmatrix} (2,2) & (0,1) \\ (1,0) & (1,1) \end{pmatrix}$$

**One Nash equilibrium in pure strategies** — the arms race:

$$\begin{pmatrix} (2,2) & (0,3) \\ (3,0) & (1,1) \end{pmatrix}$$

**No Nash equilibrium in pure strategies** — the regulation game:

$$\begin{pmatrix} (0,1) & (1,0) \\ (1,0) & (0,1) \end{pmatrix}$$

<!-- Page 15 -->

## One more example: three pure equilibria (slide 15)

A game with **three** Nash equilibria in pure strategies:

$$\begin{pmatrix} (2,2) & (2,2) \\ (2,2) & (0,1) \end{pmatrix}$$

Player 1 chooses Up or Down (rows) and Player 2 Left or Right (columns). The
equilibria are (Up, Left), (Up, Right) and (Down, Left); only (Down, Right) is
not an equilibrium. The ties in the Up row and the Left column are what generate
the extra equilibria.

<!-- Page 16 -->

## Nash equilibria? The regulation game and rock–paper–scissors (slide 16)

The slide poses the question for the two games that have no pure-strategy
equilibrium: the **regulation game**

$$\begin{pmatrix} (0,1) & (1,0) \\ (1,0) & (0,1) \end{pmatrix}$$

and **rock–paper–scissors**

$$\begin{pmatrix} (0,0) & (0,1) & (1,0) \\ (1,0) & (0,0) & (0,1) \\ (0,1) & (1,0) & (0,0) \end{pmatrix}$$

Neither has an equilibrium in pure strategies; both will have one in mixed
strategies.

<!-- Page 17 -->

## The regulation game in mixed strategies (slides 17–19)

Suppose the Firm tosses a fair coin before choosing the site and then pollutes at
Site 1 on Heads and at Site 2 on Tails. The Regulator's best response is computed
by expectation. If she checks Site 1, her expected payoff is

$$u_R(\text{Check 1}, \tfrac{1}{2}\,\text{Site 1} + \tfrac{1}{2}\,\text{Site 2}) = \tfrac{1}{2}\cdot 1 + \tfrac{1}{2}\cdot 0 = \tfrac{1}{2},$$

and if she checks Site 2 it is

$$u_R(\text{Check 2}, \tfrac{1}{2}\,\text{Site 1} + \tfrac{1}{2}\,\text{Site 2}) = \tfrac{1}{2}\cdot 0 + \tfrac{1}{2}\cdot 1 = \tfrac{1}{2}.$$

<!-- Page 18 -->

The two are equal, so the Regulator's payoff is the same whichever site she
checks, and she can play **any** mix $\alpha \in (0,1)$ of the two:

$$u_R(\tfrac{1}{2}\,\text{Site 1} + \tfrac{1}{2}\,\text{Site 2}, \alpha\,\text{Site 1} + (1-\alpha)\,\text{Site 2}) = \tfrac{1}{2}.$$

That is, any mix is a best response. Symmetrically, if the Regulator plays the
fair mix then the Firm's fair mix is a best response for the Firm.

<!-- Page 19 -->

There is a **unique** Nash equilibrium in the regulation game, and it is in mixed
strategies: the Firm plays $\tfrac{1}{2}\,\text{Site 1} + \tfrac{1}{2}\,\text{Site 2}$
and the Regulator plays
$\tfrac{1}{2}\,\text{Site 1} + \tfrac{1}{2}\,\text{Site 2}$.

<!-- Page 20 -->

## When strategies are mixed (slide 20)

A player mixes strategies only when some pure strategies result in the same
expected payoff. Two consequences follow. It never makes sense to use pure
strategies that do not maximize the expected payoff, but not all pure strategies
that do maximize it need to be used. A useful reading of mixing is as
concealment: knowing which pure strategies Player 1 uses would give Player 2 an
advantage, and mixing reduces that advantage.

<!-- Page 21 -->

## Rock–paper–scissors in mixed strategies (slide 21)

There is a **unique** Nash equilibrium in rock–paper–scissors, and it is in mixed
strategies: each player plays

$$\tfrac{1}{3}\,\text{Rock} + \tfrac{1}{3}\,\text{Paper} + \tfrac{1}{3}\,\text{Scissors}.$$

The slide leaves the proof as an exercise.

<!-- Page 22 -->

## Testing mixed-strategy equilibria: penalty kicks (slide 22)

The slide is a reference to the empirical literature on mixed strategies:
Chiappori, P.-A., S. Levitt, and T. Groseclose (2002), "Testing Mixed-Strategy
Equilibria When Players Are Heterogeneous: The Case of Penalty Kicks in Soccer",
*American Economic Review* 92 (4): 1138–1151. It is the deck's evidence that mixed
equilibria are meant to describe real play, not just to complete a classification.

<!-- Page 23 -->

## Bach or Stravinsky: pure and mixed equilibria (slide 23)

The coordination game "Bach or Stravinsky" carries both types of equilibrium:

$$\begin{pmatrix} (2,1) & (0,0) \\ (0,0) & (1,2) \end{pmatrix}$$

Two Nash equilibria are in pure strategies, (Bach, Bach) and (Stravinsky,
Stravinsky). There is one more, in mixed strategies: Friend 1 plays
$\tfrac{2}{3}\,\text{Bach} + \tfrac{1}{3}\,\text{Stravinsky}$ and Friend 2 plays
$\tfrac{1}{3}\,\text{Bach} + \tfrac{2}{3}\,\text{Stravinsky}$. The slide checks
Friend 1's expected payoff against Friend 2's mix:

$$u_1(\text{Bach}, \tfrac{1}{3}\,\text{Bach} + \tfrac{2}{3}\,\text{Stravinsky}) = 2 \times \tfrac{1}{3} + 0 \times \tfrac{2}{3} = \tfrac{2}{3},$$

$$u_1(\text{Stravinsky}, \tfrac{1}{3}\,\text{Bach} + \tfrac{2}{3}\,\text{Stravinsky}) = 0 \times \tfrac{1}{3} + 1 \times \tfrac{2}{3} = \tfrac{2}{3}.$$

The two are equal, so Friend 1 could play any mix against Friend 2's mix — the
indifference that supports the equilibrium.

<!-- Page 24 -->

## Formalities of mixed strategies (slide 24)

A strategic-form game has a set of players $N$, for each player $i \in N$ a set
of pure strategies $S_i$, and a payoff mapping
$u_i : S_1 \times \cdots \times S_N \to \mathbb{R}$. For each player, the **set of
mixed strategies** $\Delta S_i$ is the set of all probability distributions over
$S_i$. If $S_i$ is finite, then

$$\Delta S_i = \left\{ \alpha_1 s_{i1} + \cdots + \alpha_M s_{iM} \ \middle|\ \sum_{m=1}^{M} \alpha_m = 1, \ \alpha_m \ge 0 \right\}.$$

A pure strategy is a particular case of a mixed strategy, namely
$s_{ik} = 0 \times s_{i1} + \cdots + 1 \times s_{ik} + \cdots + 0 \times s_{iM}$.
Each mapping $u_i$ then extends to
$u_i : \Delta(S_1) \times \cdots \times \Delta(S_N) \to \mathbb{R}$ by linearity:

$$u_i(\alpha_1 s_{i1} + \cdots + \alpha_M s_{iM}, s_{-i}) = \alpha_1 u_i(s_{i1}, s_{-i}) + \cdots + \alpha_M u_i(s_{iM}, s_{-i}),$$

with the opponents' profile on the right still pure, and the extension continued
by linearity on every player's side.

<!-- Page 25 -->

## Nash equilibrium in mixed strategies (slide 25)

A strategy profile $(\mu_1^*, \ldots, \mu_N^*)$ is a Nash equilibrium if for any
player $i \in N$, $\mu_i^*$ is a best response to $\mu_{-i}^*$ **among all
possible mixed strategies** $\Delta S_i$:

$$u_i(\mu_i^*, \mu_{-i}^*) \ge u_i(\mu_i, \mu_{-i}^*) \quad \text{for all } \mu_i \in \Delta S_i \text{ and all } i \in N.$$

If all the strategies in a Nash equilibrium $(\mu_1^*, \ldots, \mu_N^*)$ are pure,
we say that it is a Nash equilibrium in pure strategies. This definition subsumes
the earlier one, since a pure strategy is a degenerate mixture.

<!-- Page 26 -->

## Existence of Nash equilibrium (slide 26)

**Theorem (Nash).** Any strategic-form game with a finite number of players and a
finite number of pure strategies has a Nash equilibrium. The theorem gives
existence, not uniqueness. The equilibrium might not be unique; it need not be in
pure strategies; and a game might have both pure-strategy and mixed-strategy
equilibria. In general there is no reason to think pure-strategy equilibria are
more plausible or reasonable than the mixed ones.

<!-- Page 27 -->

## Which Nash equilibrium? (slide 27)

Sometimes the Nash equilibrium is unique. Sometimes some Nash equilibria are more
plausible than others. And sometimes there is a "meta-game" that helps select a
particular equilibrium — the slide names three devices: **fictitious play**,
**mediation**, and **preliminary discussion**. The next slides give the selection
problem its classic illustration.

<!-- Page 28 -->

## Schelling's focal-point argument (slides 28–29)

The pre-cell-phone metaphor: you agreed to meet a friend at 7pm but do not
remember where. Even choosing between just two places is difficult. In this
example there is no way to tell which of the two (or even three, counting the one
in mixed strategies) Nash equilibria is better, but in other games it might be
possible. The meeting game is

$$\begin{pmatrix} (2,1) & (0,0) \\ (0,0) & (1,2) \end{pmatrix}$$

with the two locations (John Hancock and Millennium Park) as the two strategies.
<!-- Page 29 -->

The accompanying slide, Schelling's experiment, is the demonstration that people
coordinate on a **focal point** when the formal theory alone is silent.

<!-- Page 30 -->

## Not all Nash equilibria are equal (slide 30)

Let $N > 3$ people consider electing a chairman by majority vote. There are two
candidates, $A$ and $B$, and all voters prefer candidate $A$. Despite the common
preference, there are two equilibria:

$$(A, A, \ldots, A) \quad \text{and} \quad (B, B, \ldots, B).$$

Both are Nash equilibria, because no single voter can change the outcome alone.
The multiplicity here is not a focal-point coordination problem but a weakness of
the solution concept, and the remaining slides are about how to narrow the set.

<!-- Page 31 -->

## Dominated strategies (slide 31)

A strategy $s_i \in S_i$ **strictly dominates** a strategy $t_i \in S_i$ if

$$u_i(s_i, s_{-i}) > u_i(t_i, s_{-i}) \quad \text{for any profile } s_{-i} \in S_{-i},$$

and then $t_i \in S_i$ is **strictly dominated**. It **weakly dominates** $t_i$ if

$$u_i(s_i, s_{-i}) \ge u_i(t_i, s_{-i}) \ \text{for all } s_{-i} \in S_{-i} \quad \text{and there exists } t_{-i} \in S_{-i} \text{ with } u_i(s_i, t_{-i}) > u_i(t_i, t_{-i}),$$

and then $t_i \in S_i$ is **weakly dominated**. The difference is precisely the
strictness of the comparison at some profile.

<!-- Page 32 -->

## Dominated strategies in Nash equilibria (slide 32)

**Proposition.** A strictly dominated strategy cannot be used in any Nash
equilibrium. A weakly dominated strategy, by contrast, can be used in a Nash
equilibrium. The slide points back to $(B, B, \ldots, B)$ as the example, so weak
dominance does not survive into the equilibrium restriction the way strict
dominance does.

<!-- Page 33 -->

## An example: weak dominance (slide 33)

Player 1 chooses Up or Down, Player 2 Left or Right:

$$\begin{pmatrix} (2,2) & (2,2) \\ (2,2) & (0,1) \end{pmatrix}$$

Player 1's Down is weakly dominated and Player 2's Right is weakly dominated.
There are three Nash equilibria in pure strategies — (Up, Left), (Up, Right) and
(Down, Left) — and exactly one of them, (Up, Left), uses no dominated strategy.

<!-- Page 34 -->

## Another example: the payoff-maximizing equilibrium in dominated strategies (slide 34)

$$\begin{pmatrix} (1,1) & (2,0) \\ (0,2) & (2,2) \end{pmatrix}$$

Player 1's Down is weakly dominated and Player 2's Right is weakly dominated.
There are two pure-strategy Nash equilibria, (Up, Left) and (Down, Right), and the
payoff-maximizing one, (Down, Right) with payoffs $(2,2)$, is built entirely from
weakly dominated strategies. The slide closes with a question: is it possible to
have a game whose only Nash equilibrium is in dominated strategies?

<!-- Page 35 -->

## The arms race: strictly dominant strategies (slide 35)

In the arms race both players have a strictly dominated strategy, "Don't build
bombs":

$$\begin{pmatrix} (2,2) & (0,3) \\ (3,0) & (1,1) \end{pmatrix}$$

so "Build bombs" strictly dominates it for each player, and the only Nash
equilibrium, (Build, Build), is in strictly dominant strategies.

<!-- Page 36 -->

## Not all Nash equilibria are equal, continued (slide 36)

Returning to the majority-vote game, $(A, A, \ldots, A)$ is a Nash equilibrium in
undominated strategies while $(B, B, \ldots, B)$ is a Nash equilibrium in weakly
dominated strategies. When $N$ is large the game has many pure-strategy Nash
equilibria, but only one equilibrium without dominated strategies.

<!-- Page 37 -->

## An algorithm for finding equilibria (slide 37)

1. Eliminate strictly dominated strategies — they can never be part of a Nash
   equilibrium, and sequential elimination is possible.
2. Check whether there are pure-strategy equilibria in the remaining game.
3. Find all mixed-strategy equilibria; $2 \times K$ games are treated in the TA
   session.

<!-- Page 38 -->

## Elimination of dominated strategies and equilibrium (slide 38)

Three statements. A strictly dominated strategy cannot be used in any Nash
equilibrium. A strategy that is eliminated by **sequential** elimination of
strictly dominated strategies also cannot be used in any Nash equilibrium. But a
weakly dominated strategy can be used in a Nash equilibrium, so the elimination
procedure is valid for strict dominance only.

<!-- Page 39 -->

## Sequential elimination: an example (slides 39–40)

The closing example is a five-by-five game, with Player 1's strategies $A$–$E$ in
the rows and Player 2's $1$–$5$ in the columns:

$$\begin{pmatrix} (2,3) & (5,4) & (-8,1) & (-2,-3) & (0,1) \\ (1,2) & (-5,5) & (4,6) & (0,0) & (2,9) \\ (3,1) & (0,1) & (3,2) & (8,-1) & (5,5) \\ (0,0) & (4,6) & (2,3) & (1,3) & (-5,5) \\ (8,0) & (3,8) & (0,5) & (3,2) & (3,7) \end{pmatrix}$$

<!-- Page 40 -->

The slide prescribes the elimination order: eliminate column [4] as it is
strictly dominated by [5]; eliminate [1] and [3] as each is strictly dominated by
a mix of [2] and [5]; eliminate row B as it is strictly dominated (now) by C;
eliminate row D as it is strictly dominated by a mix of A and E. Note that
dominance is taken against mixtures as well as pure strategies — a strategy can
be dominated by a mix of the remaining ones — which is why the order matters and
the procedure is not merely mechanical.

## Difficulty checklist

1. **Best response is a weak inequality.** The definition uses "$\ge$", not
   "$>$" (slide 7), and the ties it admits are exactly what let several
   equilibria coexist; treating "best response" as "unique best response" breaks
   every coordination example (slides 12, 14, 15).
2. **Equilibrium counts are pure-strategy counts unless stated.** Slide 3's
   three cases (one, two, none) describe pure strategies, and the regulation game
   does have an equilibrium once mixtures are allowed (slides 16–19). Do not read
   "no pure equilibrium" as "no equilibrium".
3. **Mixing requires indifference.** A player mixes only over pure strategies
   that all yield the same expected payoff, and need not use every such strategy;
   a mixture putting weight on a strictly worse pure strategy is not a best
   response (slides 20, 23).
4. **Existence is not uniqueness.** Nash's theorem guarantees at least one
   equilibrium in a finite game, not a unique one and not a pure one; a game can
   have both pure and mixed equilibria, and neither type is intrinsically more
   plausible (slides 25–27).
5. **A pure strategy is a special case of a mixed strategy.** It is a degenerate
   distribution in $\Delta S_i$ (slide 24); keep the containment straight when
   counting equilibria.
6. **Strict dominance survives, weak dominance does not.** A strictly dominated
   strategy lies in no equilibrium, but a weakly dominated one lies in some —
   $(B, B, \ldots, B)$ and (Down, Right) are the two examples (slides 30–36).
7. **Sequential elimination is for strict dominance only.** The algorithm
   eliminates strictly dominated strategies, including dominance by a mixture,
   and is safe precisely because strict dominance cannot appear in any
   equilibrium; running the same procedure on weak dominance is invalid (slides
   37–38).
8. **Payoff-maximizing does not mean undominated.** In slide 34 the best outcome,
   (Down, Right), is the one built from weakly dominated strategies; payoff size
   is not a proxy for plausibility (slide 34).
9. **Two equilibria can be the same story.** The coordination game's two pure
   equilibria are mirror images, and the problem is not that one is better but
   that the theory alone does not choose (slides 6, 12, 28).
10. **Focal points come from outside the game.** Schelling's argument supplies
    selection where the formal model is silent, and fictitious play, mediation
    and preliminary discussion are the three devices the deck names (slides
    27–29).
