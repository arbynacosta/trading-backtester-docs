<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.BacktesterStrategy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="buy"/>
<meta itemprop="property" content="cancel"/>
<meta itemprop="property" content="cancel_all"/>
<meta itemprop="property" content="exit"/>
<meta itemprop="property" content="exit_all"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="next"/>
<meta itemprop="property" content="nextstart"/>
<meta itemprop="property" content="order"/>
<meta itemprop="property" content="prenext"/>
<meta itemprop="property" content="sell"/>
<meta itemprop="property" content="start"/>
<meta itemprop="property" content="stop"/>
</div>

# bt.BacktesterStrategy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Base backtester strategy class.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.BacktesterStrategy(
    backtester: Backtester,
    parameters: (dict | AttrDict | None) = None
)
</code></pre>



<!-- Placeholder for "Used in" -->


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`backtester`
</td>
<td>
The parent backtester. Must be an instance of
<a href="..\bt\Backtester.md"><code>bt.Backtester</code></a>.
</td>
</tr><tr>
<td>
`parameters`
</td>
<td>
Strategy parameters that are used as overrides
over the strategy parameters set in the parent backtester's
internal configuration.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`backtester`
</td>
<td>
The parent backtester. An instance of <a href="..\bt\Backtester.md"><code>bt.Backtester</code></a>.
</td>
</tr><tr>
<td>
`bt`
</td>
<td>
Shorthand for easier access of the backtester instance.
</td>
</tr><tr>
<td>
`config`
</td>
<td>
Backtester configuration. An instance of <a href="..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a>.
</td>
</tr><tr>
<td>
`data`
</td>
<td>
OHLCV data exposure from the internal exchange.
</td>
</tr><tr>
<td>
`p`
</td>
<td>
Shorthand for easier access of parameters.
</td>
</tr><tr>
<td>
`parameters`
</td>
<td>
Strategy parameters.
</td>
</tr>
</table>



## Methods

<h3 id="buy"><code>buy</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L116-L128">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>buy(
    order_id: str = &#x27;order-id&#x27;,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None
) -> Order
</code></pre>

Go long or reduce/close a short position.


<h3 id="cancel"><code>cancel</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L171-L177">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel(
    order_or_id: (Order | str)
)
</code></pre>

Cancels a pending order by referencing the order or its ID.

See the documentation for <a href="..\bt\BacktesterExchange.md#cancel"><code>bt.BacktesterExchange.cancel()</code></a>
for an explanation of what the different function arguments are.

<h3 id="cancel_all"><code>cancel_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L167-L169">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel_all()
</code></pre>

Cancels all pending orders.


<h3 id="exit"><code>exit</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L183-L198">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit(
    order_or_id: (Order | str),
    amount: (float | None) = None,
    amount_percent: (float | None) = None
)
</code></pre>

Exit a trade by referencing the order or its ID.

See the documentation for <a href="..\bt\BacktesterExchange.md#exit"><code>bt.BacktesterExchange.exit()</code></a>
for an explanation of what the different function arguments are.

<h3 id="exit_all"><code>exit_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L179-L181">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit_all()
</code></pre>

Exits all trades.


<h3 id="initialize"><code>initialize</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L46-L69">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>initialize()
</code></pre>

Data initialization for the strategy.

This function is where all the indicator data are calculated.
Only runs once and it runs when the strategy class is
initialized. Similar to how the `__init__` function works.

The correct way of adding a new indicator is by creating a new
attribute in the `self` variable. The value should be an
instance of `pd.Series` which is usually the result of our
TA functions.

```python
from trading.backtester import ta

self.ema50 = ta.ema(self.close, timeperiod=50)

# Use `indicator_period` parameter from configuration
self.another_indicator = ta.ema(self.close, timeperiod=self.p.period)
```

This function can also be used to initialize new variables that
can help the overall strategy.

<h3 id="next"><code>next</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L102-L111">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>next()
</code></pre>

Runs after the minimum indicator period is reached.

This is the main function of the strategy. The different order
functions are used here to generate long or short signals.

See the documentation for <a href="..\bt\BacktesterStrategy.md#prenext"><code>BacktesterStrategy.prenext()</code></a> for an
explanation of what the minimum indicator period is.

<h3 id="nextstart"><code>nextstart</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L92-L100">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>nextstart()
</code></pre>

Runs when the minimum indicator period is reached.

See the documentation for <a href="..\bt\BacktesterStrategy.md#prenext"><code>BacktesterStrategy.prenext()</code></a> for an
explanation of what the minimum indicator period is.

<h3 id="order"><code>order</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L144-L165">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>order(
    order_id: str,
    position: str,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None
) -> Order
</code></pre>

Lower-level order creation function.

See the documentation for <a href="..\bt\BacktesterExchange.md#order"><code>bt.BacktesterExchange.order()</code></a>
for an explanation of what the different function arguments are.

<h3 id="prenext"><code>prenext</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L74-L90">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>prenext()
</code></pre>

Runs before the minimum indicator period is reached.

There are different indicators used in a strategy and some of
these indicators have different required number of periods
before they can be used. The largest required indicator period
is called the "minimum indicator period".

For Example, our strategy uses this list of indicators:
- EMA 200 (required number of periods is 200)
- SMA 50 (required number of periods is 50)
- RSI 14 (required number of periods is 14)

So for this strategy, the minimum indicator period is 200 since
that's the largest required indicator period. Given this,
`prenext()` is called while period is less than 200.

<h3 id="sell"><code>sell</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L130-L142">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>sell(
    order_id: str = &#x27;order-id&#x27;,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None
) -> Order
</code></pre>

Go short or reduce/close a long position.


<h3 id="start"><code>start</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L71-L72">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>start()
</code></pre>

Runs at the first period of each asset of a backtest run.


<h3 id="stop"><code>stop</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L113-L114">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>stop()
</code></pre>

Runs at the end of the backtest run.




