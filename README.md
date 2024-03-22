# Information Pooling in Second Price Auctions


See the pdf file for a compiled version.

# Summary of the Proposal

This research offers a joint consideration to two distinct problems in
second-price auctions with common values: seller's optimal supply of
information precision and bidders' incentive to acquire information.
Normality assumption is adopted to allow for the utilization of
different notions of stochastic ordering of signals simultaneously in a
highly tractable learning environment. The main contribution is aimed to
be enabling cooperative behavior among bidders through introduction of
an *information pool*. Resulting environment can potentially lead to
novel strategic considerations between the seller and the bidders who
aim to capture larger shares of the total surplus.

# Background

Following [@milgrom1982theory]'s seminal results, it's widely accepted
that publicly revealing information cannot hurt the seller in the common
value setting. In their setup, valuations are characterized as functions
of public and/or private signals; whereas for the setting considered in
this research, signals are solely information sources from which
valuation can be inferred. This divergence from the mainstream
literature poses considerable challenges and it's of interest of this
research to investigate the robustness of classical results under this
alternative characterization.

[@ganuza2010signal] consider optimal supply of signal precision, where
for signals that can be ordered by *supermodular precision*, authors
show that in SPA with independent and private (but uncertain) values,
optimal level of precision supplied by the auctioneer is lower than the
socially efficient level. Intuitively, this is a result of a trade-off
concerning seller's incentive to supply information: higher precision
results in higher efficiency and increases total surplus, while
simultaneously making bidders more heterogeneous and increasing winning
bidder's information rents, hence lowering seller's share of surplus.
Their resulting conclusion is that under private values, seller can not
be relied on to disclose all socially desirable information. From the
bidders' perspective, [@persico2000information] discusses bidders'
incentives to acquire more precise information, where in a general value
SPA framework it's shown that for exogenously supplied, *affiliated* and
*accuracy ordered* signals, expected bidder payoff is non-decreasing in
the accuracy of the signal. His setup also considers value as a function
of signals, which is not the case here.

# Goal and Objectives 

The aim of this research is to jointly consider these two frameworks
through endogenizing bidders' information acquisition process by letting
bidders pool their private signals that are supplied by the seller. The
setting can be seen as a primitive abstraction of communication through
formation of social groups in a competitive environment. While the exact
scenario treated here may be hard to come by in real cases; I think it's
sensible to think that personal judgments of value (especially the
accuracy of the judgment) are usually shaped through direct or indirect
communication. Main limitation of this research is the restriction of
the setting to common values to enable bidders to learn from each
others' signals, as under Bayesian updating each signal has to be
conditioned on the same random variable.

Bidders' incentive to participate in the information pool is
characterized as acquiring more precise information regarding the common
value. Following [@persico2000information]'s result, participation
decision might seem to be straight-forward, although with one caveat:
here, a bidder's decision to obtain more precise information
simultaneously allows other bidders to do the same. Thus, in particular,
the effect on the distribution of second-highest bid should be of
concern when analyzing the optimal participation decision.

Regarding the seller's decision, the framework proposed in
[@ganuza2010signal] considers private values. Since in their paper, the
adverse effect of higher precision on seller's revenue is due to an
increase in information rents (following higher heterogeneity of bidder
valuations), it's unclear whether this effect is sustained under common
values. Another concern is that, while generally increasing
participation is seen as beneficial for the seller, here, it may also
increase the size of the information pool, potentially leading to
undesirably high precision levels for the seller. One strategic
consideration here might be that seller may anticipate future
communication among bidders and under-supply precision accordingly;
while another one might be to restrict bidder entry.

# Model

## Setup 

Formally, let there be $n \geq 2$ ex-ante identical risk neutral bidders
who have an unknown common value $v$ for a single indivisible object
that's being sold in a second-price sealed-bid auction with no reserve
price. Bidders treat the common value as a random variable $V$ and hold
the common prior belief such that $V \sim N(v,\rho_{0}^{-1})$. What's
explicitly known to bidders (and what is of central importance) is the
precision level of this belief. Before the auction, seller has the
opportunity to produce private signals $(X_{i}^\rho)_{i=1}^n$ of
precision $\rho$ that are identically and independently distributed with
$X_i \mid V \sim N(v,\rho^{-1})$. Upon receiving their signals (in
addition to learning from their own signal) bidders may choose to
participate in an information pool, where they can truthfully share
their private signal realizations and learn from other bidders' signal
realizations in the pool. The learning process is characterized by
Bayesian updating and hence if first $n \geq k \geq 2$ bidders choose to
participate in the information pool, each bidder in the pool then have
$k-1$ additional signals conditioned on $V$ that they can use to
sequentially update their prior beliefs. Bidder $i$'s posterior belief
on the common value if she chooses not to participate in the information
pool is $$V \mid X_i=x_i \sim N(v,[\rho_0 + \rho]^{-1})$$ whereas, if
she chooses to participate with $k-1$ other bidders is
$$V \mid X_1=x_1,...,X_k=x_k \sim N(v,[\rho_0 + k\rho]^{-1})$$ For ease
of computation, it's without loss to think about updating the prior
belief with $k$ signals from distribution $N(v, \rho^{-1})$, as updating
it with one *aggregate* signal from distribution $N(v, [k\rho]^{-1})$ in
terms of the posterior distributions they generate. Let $\Phi$,
$\Phi^I$, $\Phi'^I$, $\Phi_k^P$ and $\Phi_k'^P$ denote the cumulative
distribution functions of: prior belief; individual signal; prior belief
updated with individual signal realization; aggregate signal from a pool
of size $k$ and prior belief updated with this aggregate signal
realization, respectively. Then, pool participation decision can be
partially reformulated as acquiring the signal with conditional c.d.f.
$\Phi_k^P$ or $\Phi^I$, where latter is a *mean-preserving spread* of
the former.

## Bidders' Incentives {#bidders-incentives .unnumbered}

Bidders know about the precision level chosen by the seller and make the
pool participation decision based on the anticipated precision level of
their posterior beliefs. Participating in the pool allows access to
additional signal realizations, hence, enables bidders to construct a
more precise posterior belief. This opportunity simultaneously allows
other bidders in the pool to do the same, which might potentially be a
drawback.

As a first attempt, it's instructive to check whether full participation
in the information pool can be an equilibrium. Assuming all bidders but
bidder $i$ participate in the information pool, if bidder $i$ chooses to
participate, each bidder would then symmetrically update their prior
belief using $n$ signal realizations. Then, bidder $i$'s optimal bid in
the SPA given signal realizations $\boldsymbol{x}=(x_1,...,x_n)$ and her
resulting posterior belief can be characterized as,
$$b_i^P(\boldsymbol{x}) \in \arg\max_{b} \int_{-\infty}^{\infty} [V - W(\boldsymbol{x})]\mathbf{1}_{\{W(\boldsymbol{x})<b\}} \,d\Phi_n'^P(V\mid \boldsymbol{X}=\boldsymbol{x})$$
where $W(\boldsymbol{x})=max_{i \neq j}b_j(\boldsymbol{x})$ and
$\mathbf{1}$ is the indicator function. This characterization allows the
bidder to adjust her bid to win as long as her expected valuation is
larger than the price paid. In the IPV setting, knowledge of the true
valuation allows the bidder to perfectly adjust this level of optimal
bid, which is equal to the value itself. As this is not the case here,
expectation is considered instead, which makes the precision of belief
crucial. With a more precise judgment on the true value, bidders should
be able to increase their bid for higher winning probability with a
lower risk of bidding above their value.

If she chooses not to participate, she will only update her prior with
her individual signal, where other bidders will use $n-1$ signals to
update their priors before placing their bids. Hence, compared to the
first scenario, accuracy will be lower for all bidders, but
(potentially) much lower for bidder $i$. In this case, bidder $i$'s
optimal bid is
$$b_i^I(x_i) \in \arg\max_{b} \int_{-\infty}^{\infty} [V - W(\boldsymbol{x_{-i}})]\mathbf{1}_{\{W(\boldsymbol{x_{-i}})<b\}} \,d\Phi'^I(V\mid X_i=x_i)$$
where $W(\boldsymbol{x_{-i}})=max_{i \neq j}b_j(\boldsymbol{x_{-i}})$
and $\boldsymbol{x_{-i}}=(x_1,...,x_{i-1},x_{i+1},...,x_n)$. It should
be noted that signal realizations affect bids primarily through
posterior beliefs that they shape. In particular and in contrast to the
mainstream literature, I expect equilibrium bid functions to be
indifferent to specific signal realizations and that they only change
according to the number of accessible signals (i.e. according to the
precision of posterior belief).

Ultimately, it's desired to compare resulting payoffs in these two
situations to determine whether it's beneficial for bidder $i$ to
participate in the pool. One approach to evaluate different payoffs can
be through reformulating the problem into the general decision problem
setting given in [@persico2000information], although it's unclear
whether their method holds with an arbitrary number of bidders.
Alternatively, it seems sensible to approach the solution of stochastic
maximization problems by potentially imposing additional structure on
the (symmetric) bidding functions to compare resulting payoffs in two
cases. Due to the tractable environment, distribution of second-order
statistic can also be explicitly calculated in each case to determine an
expectation for the price level.

## Seller's Incentive 

Seller chooses the level of precision $\rho$ as to maximize her expected
revenue, which is equivalent to maximizing the second-highest bid.
Before approaching this problem explicitly, it's essential to construct
an equilibrium bidding behavior involving bid functions and
participation decision for an arbitrary level of precision. If such an
equilibrium can be constructed, then the optimum level of precision may
be computed from the distribution of second-highest bid.

Due to the common value setting, it might seem that supplying the
highest precision should be optimal for the seller. Then, posterior
beliefs would be single-point distributions, where each bidder exactly
knows the true value and bids away their information rents resulting in
full revenue extraction by the seller. This general conclusion doesn't
apply to this setting for one simple reason: bidders may bid above the
common value in the presence of uncertainty. For simplicity, assume each
bidder participates in the pool and bids randomly according to the
resulting posterior belief on the value. Then, expectation of the
second-highest bid equals to the expectation of second-order statistic
of $n$ draws from $\Phi_n'^P$. This statistic then has the following
cumulative distribution function[^1]
$$F_2(y)=n[\Phi_n'^P(y)]^{n-1}-(n-1)[\Phi_n'^P(y)]^n$$ which can be used
to explicitly compute the expected revenue. It should be clear without
calculation that expected price can be greater than the mean and hence
greater than the common value.

## Alternative Characterization

Main challenge of this research is due to the common value setting,
where desirable properties of SPA aren't easily accessible. As
mentioned, this constraint follows from the restriction of Bayesian
updating. Alternatively, it may be possible to utilize other methods for
belief updating that may potentially allow for a private value setup.
Additionally, properties of supermodular precision, accuracy order,
*integral order* and second-order stochastic dominance can be used to
obtain results, as mean-preserving spreads of normal distributions
satisfy these stochastic orders.

[^1]: See [@krishna2010auction]