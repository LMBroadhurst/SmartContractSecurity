## Liquidity Pool
In a `decentralised 'uniswap like' exchange`, traders do not directly trade with each other. They trade with a token pool
that contains a pair of ERC20 tokens. The pool contains a reserve of both tokens, for example ETH / OP.

The way that Liquidity Pools gain their liquidity, or reserves, is via `Liquidity Providers` who deposit their tokens into
the pool. `Liquidity Providers` are incentivised to add liquidity to a pool because they will earn rewards from the swap fees
that are generated by traders who want to exchange their tokens.

Each independent liquidity pool contains its own ERC20 pair - users who want to trade X for Y will be directed to the relevant
liquidity pool.

## X x Y = K
Example LPA: 5 ETH & 20 OP / 5X & 20Y / Ratio = 1 ETH : 4 OP

If Jeff wants to swap 1 ETH for OP*, the new ETH / X balance becomes 6 ETH / X.

Since K must remain unchanged, the new Y can be calculated from the formula: `X x Y = newX * newY`

This is rearranged to `X x Y / newX = newY` => `5 x 20 / 6 = 16.67`

Now we can simply do `Y - newY = receivedTokens` => `20 - 16.67 = 3.32`

Jeff therefore receives 3.32 OP. The pool now has 6 ETH and 16.68 OP.

// The following assumes no fees. * denotes where fees would be introduced (pre-swap).

### Economic impact of the swap

The new Example LPA: 6 ETH & 16.68 OP / 6X & 16.68Y / Ratio = 1 ETH : 2.78 OP

Clearly the swap has had a major price impact.

We can see how if Jeff kept swapping ETH for OP, the ration of ETH & OP would keep decreasing, reducing the relative price of ETH
and increasing the relative price of OP. Basic supply & demand.

This problem is exacerbated by the small values shown in the example, for large liquidity pools this is not a problem.

Bots that could take advantage or arbitrage opportunities may attempt to take advantage of this, but in doing so increase
demand or supply for the pair and therefore level out the price.

Large liquidity pools almost always have a price close or at the market price.