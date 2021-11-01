<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.Backtester" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="run"/>
<meta itemprop="property" content="set_strategy"/>
<meta itemprop="property" content="visualize"/>
</div>

# bt.Backtester

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Base backtester class.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.Backtester(
    config: (dict | str | BacktesterConfig)
)
</code></pre>



<!-- Placeholder for "Used in" -->




<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`config`
</td>
<td>

</td>
</tr><tr>
<td>
`exchange`
</td>
<td>

</td>
</tr><tr>
<td>
`metrics`
</td>
<td>

</td>
</tr><tr>
<td>
`minimum_indicator_period`
</td>
<td>
Minimum number of periods for indicator warmup.

There are different indicators used in a strategy and some of
these indicators have different required number of periods
before they can be used. The largest required indicator period
is called the "minimum indicator period".

For Example, our strategy uses this list of indicators:
- EMA 200 (required number of periods is 200)
- SMA 50 (required number of periods is 50)
- RSI 14 (required number of periods is 14)

So for this strategy, the minimum indicator period is 200 since
that's the largest required indicator period. If there's no
strategy parameters, the minimum indicator period is 0.
</td>
</tr><tr>
<td>
`strategy`
</td>
<td>
The strategy to be used for the backtester.

To set the strategy properly, use <a href="..\bt\Backtester.md#set_strategy"><code>Backtester.set_strategy()</code></a>.
</td>
</tr>
</table>



## Methods

<h3 id="run"><code>run</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\backtester.py#L39-L147">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>run()
</code></pre>

The core method to perform backtesting.


<h3 id="set_strategy"><code>set_strategy</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\backtester.py#L149-L186">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>set_strategy(
    strategy: BacktesterStrategy,
    parameters: (dict | None) = None
)
</code></pre>

Sets the strategy to be used by the Backtester.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`strategy`
</td>
<td>
A subclass of the <a href="..\bt\BacktesterStrategy.md"><code>bt.BacktesterStrategy</code></a> class.
</td>
</tr><tr>
<td>
`parameters`
</td>
<td>
A dictionary containing a set of strategy
parameters. If the configuration given to the Backtester
already has a set of parameters and the user still
entered another set of parameters in this function,
the latter is the one we would use.
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
Raised when the strategy is not a subclass of
<a href="..\bt\BacktesterStrategy.md"><code>bt.BacktesterStrategy</code></a>, is not a class at all, or if
the input strategy is already an instance.
</td>
</tr>
</table>



<h3 id="visualize"><code>visualize</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\visuals.py#L17-L308">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>visualize(
    input_symbol: (str | None) = None,
    plots: (list | dict | str | None) = None
) -> (go.Figure | None)
</code></pre>

Visualization function for the backtester.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`input_symbol`
</td>
<td>
The asset symbol that we want to visualize. If
set to `None`, then the results of the visualization is for
the overall backtest result.
</td>
</tr><tr>
<td>
`plots`
</td>
<td>
A list of strings indicating the indicators, and other
charts that we want to include in the visualization.
</td>
</tr>
</table>





