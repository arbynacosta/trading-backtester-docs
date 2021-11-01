<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.BacktesterStrategy" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="buy"/>
<meta itemprop="property" content="cancel"/>
<meta itemprop="property" content="cancel_all"/>
<meta itemprop="property" content="end"/>
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
An instance of the parent backtester.
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

</td>
</tr><tr>
<td>
`bt`
</td>
<td>
Shorthand for self.backtester.
</td>
</tr><tr>
<td>
`config`
</td>
<td>

</td>
</tr><tr>
<td>
`p`
</td>
<td>
Shorthand for self.parameters.
</td>
</tr><tr>
<td>
`parameters`
</td>
<td>

</td>
</tr>
</table>



## Methods

<h3 id="buy"><code>buy</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L103-L116">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>buy(
    order_id: str = &#x27;buy&#x27;,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None,
    leverage: float = 1
) -> Order
</code></pre>

Go long or reduce/close a short position.


<h3 id="cancel"><code>cancel</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L162-L168">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel(
    order_or_id: (Order | str)
)
</code></pre>

Cancels a pending order by referencing the order or its ID.

See the documentation for `bt.BacktesterExchange.cancel()`
for an explanation of what the different function arguments are.

<h3 id="cancel_all"><code>cancel_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L158-L160">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel_all()
</code></pre>

Cancels all pending orders.


<h3 id="end"><code>end</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L72-L73">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>end()
</code></pre>

Runs at the last period of each asset of a backtest run.


<h3 id="exit"><code>exit</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L174-L180">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit(
    order_id: str
)
</code></pre>

Exit a trade by referencing the order or its ID.

See the documentation for `bt.BacktesterExchange.exit()`
for an explanation of what the different function arguments are.

<h3 id="exit_all"><code>exit_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L170-L172">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit_all()
</code></pre>

Exits all trades.


<h3 id="initialize"><code>initialize</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L44-L67">View source</a>

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

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L89-L98">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>next()
</code></pre>

Runs after the minimum indicator period is reached.

This is the main function of the strategy. The different order
functions are used here to generate long or short signals.

See documentation for <a href="..\bt\Backtester.md#minimum_indicator_period"><code>bt.Backtester.minimum_indicator_period</code></a>
for an explanation of what the minimum indicator period is.

<h3 id="nextstart"><code>nextstart</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L82-L87">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>nextstart()
</code></pre>

Runs when the minimum indicator period is reached.

See documentation for <a href="..\bt\Backtester.md#minimum_indicator_period"><code>bt.Backtester.minimum_indicator_period</code></a>
for an explanation of what the minimum indicator period is.

<h3 id="order"><code>order</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L133-L156">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>order(
    order_id: str,
    position: str,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None,
    leverage: float = 1
) -> Order
</code></pre>

Lower-level order creation function.

See the documentation for `bt.BacktesterExchange.order()`
for an explanation of what the different function arguments are.

<h3 id="prenext"><code>prenext</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L75-L80">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>prenext()
</code></pre>

Runs before the minimum indicator period is reached.

See documentation for <a href="..\bt\Backtester.md#minimum_indicator_period"><code>bt.Backtester.minimum_indicator_period</code></a>
for an explanation of what the minimum indicator period is.

<h3 id="sell"><code>sell</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L118-L131">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>sell(
    order_id: str = &#x27;sell&#x27;,
    limit: (float | None) = None,
    stop: (float | None) = None,
    amount: (float | None) = None,
    amount_percent: (float | None) = None,
    leverage: float = 1
) -> Order
</code></pre>

Go short or reduce/close a long position.


<h3 id="start"><code>start</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L69-L70">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>start()
</code></pre>

Runs at the first period of each asset of a backtest run.


<h3 id="stop"><code>stop</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\strategy.py#L100-L101">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>stop()
</code></pre>

Runs at the last period of each asset of a backtest run.




