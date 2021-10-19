<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.BacktesterExchange" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="cancel"/>
<meta itemprop="property" content="cancel_all"/>
<meta itemprop="property" content="exit"/>
<meta itemprop="property" content="exit_all"/>
<meta itemprop="property" content="nextstart"/>
<meta itemprop="property" content="nextstop"/>
<meta itemprop="property" content="order"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="start"/>
<meta itemprop="property" content="stop"/>
</div>

# bt.BacktesterExchange

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Exchange/Broker abstraction for the backtester.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.BacktesterExchange(
    backtester: Backtester,
    initial_balance: float = 10000,
    currency: str = &#x27;USD&#x27;
)
</code></pre>



<!-- Placeholder for "Used in" -->

This represents a hyper exchange that can download any data from any
real exchange and it also contains all the balance, orders, trades,
and positions information.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`backtester`
</td>
<td>
The instance of the this exchange's backtester.
</td>
</tr><tr>
<td>
`initial_balance`
</td>
<td>
Initial balance of the exchange when an
instance is created
</td>
</tr><tr>
<td>
`currency`
</td>
<td>
Determines the quote currency of the balance
and the PnL and value of positions in the exchange.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`asset_balances`
</td>
<td>

</td>
</tr><tr>
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

</td>
</tr><tr>
<td>
`cancelled_orders`
</td>
<td>

</td>
</tr><tr>
<td>
`closed_trades`
</td>
<td>

</td>
</tr><tr>
<td>
`currency`
</td>
<td>

</td>
</tr><tr>
<td>
`data`
</td>
<td>

</td>
</tr><tr>
<td>
`equity`
</td>
<td>

</td>
</tr><tr>
<td>
`initial_balance`
</td>
<td>

</td>
</tr><tr>
<td>
`open_trades`
</td>
<td>

</td>
</tr><tr>
<td>
`pending_orders`
</td>
<td>

</td>
</tr><tr>
<td>
`positions`
</td>
<td>

</td>
</tr><tr>
<td>
`wallet_balance`
</td>
<td>

</td>
</tr>
</table>



## Methods

<h3 id="cancel"><code>cancel</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L263-L311">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel(
    order_or_id: (Order | str)
)
</code></pre>

Cancels a pending order by referencing the order or its ID.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`order_or_id`
</td>
<td>
Used to identify the orders in the exchange. If
this is a string, it is considered as a order ID. If its
an `Order` object then the order itself is deleted from
the list of pending orders.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Raises</th></tr>

<tr>
<td>
`OrderNotFoundError`
</td>
<td>
Raised when the exchange can't find any
pending orders relating to the `order_or_id` input.
</td>
</tr>
</table>



<h3 id="cancel_all"><code>cancel_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L258-L261">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cancel_all()
</code></pre>

Cancels all pending orders.


<h3 id="exit"><code>exit</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L322-L392">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit(
    order_id: (Order | str),
    amount: (float | None) = None,
    amount_percent: (float | None) = None
)
</code></pre>

Exit a trade with the specified ID.

If there were multiple entry orders with the same ID, all of
them are exited at once. If there are no open entries with the
specified ID by the moment the function is called, the function
will not have any effect.

The command uses market order. Every entry is closed by a
separate market order.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`order_id`
</td>
<td>
Used to identify the orders in the exchange.
</td>
</tr><tr>
<td>
`signal_source_symbol`
</td>
<td>
Signal-source symbol of the asset
where the order is being made on.
</td>
</tr><tr>
<td>
`amount`
</td>
<td>
Optional order amount in the exchange currency.
</td>
</tr><tr>
<td>
`amount_percent`
</td>
<td>
Optional order amount (in percentage) in the
exchange currency. This argument takes precedence over
the `amount` parameter. If both are not provided, the
order will use the available wallet balance as basis.
</td>
</tr>
</table>



<h3 id="exit_all"><code>exit_all</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L313-L320">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>exit_all()
</code></pre>

Exits all trades.


<h3 id="nextstart"><code>nextstart</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L103-L104">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>nextstart()
</code></pre>

Runs at the start of each period.


<h3 id="nextstop"><code>nextstop</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L106-L135">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>nextstop()
</code></pre>

Runs after the end of every period in the data.


<h3 id="order"><code>order</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L140-L256">View source</a>

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

Create an order.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`order_id`
</td>
<td>
Used to identify the orders in the exchange.
</td>
</tr><tr>
<td>
`position`
</td>
<td>
The position of the order. Value can either be
"long" or "short".
</td>
</tr><tr>
<td>
`limit`
</td>
<td>
Optional order limit price in the exchange currency.
If both `limit` and `stop` prices are `None`, the order
type is market order.
</td>
</tr><tr>
<td>
`stop`
</td>
<td>
Optional order stop price in the exchange currency.
If both `limit` and `stop` prices are `None`, the order
type is market order.
</td>
</tr><tr>
<td>
`amount`
</td>
<td>
Optional order amount in the exchange currency.
</td>
</tr><tr>
<td>
`amount_percent`
</td>
<td>
Optional order amount (in percentage) in the
exchange currency. This argument takes precedence over
the `amount` parameter. If both are not provided, the
order will use the available wallet balance as basis.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Raises</th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
Raised when the input position type is not
found in the list of valid values. Check out
`trading.backtester.position.VALID_POSITION_TYPES` for
the list of valid values.
</td>
</tr><tr>
<td>
`InsufficientBalanceError`
</td>
<td>
Raised when the remaining wallet
balance in the exchange is no longer enough to create
an order.
</td>
</tr><tr>
<td>
`ValueError`
</td>
<td>
Raised when number arguments are negative
numbers or zero.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Return</th></tr>
<tr class="alt">
<td colspan="2">
The created order instance. This is only for the user's
copy. The order returned is automatically added to the
exchange's record of pending orders.
</td>
</tr>

</table>



<h3 id="reset"><code>reset</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L97-L98">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>reset()
</code></pre>




<h3 id="start"><code>start</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L100-L101">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>start()
</code></pre>

Runs at the very first period of a backtest run.


<h3 id="stop"><code>stop</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\exchange.py#L137-L138">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>stop()
</code></pre>

Runs at the end of the backtest run.




