<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.BacktesterConfig" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_dict"/>
<meta itemprop="property" content="from_json"/>
<meta itemprop="property" content="load"/>
<meta itemprop="property" content="postvalidation"/>
<meta itemprop="property" content="prevalidation"/>
</div>

# bt.BacktesterConfig

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Class representation of a backtester configuration.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.BacktesterConfig(
    strategy_parameters: AttrDict,
    initial_balance: float,
    initial_balance_currency: str,
    shared_balance: bool,
    trading_exchange: str,
    starting_timestamp: str,
    ending_timestamp: str,
    assets: list[AssetConfig]
)
</code></pre>



<!-- Placeholder for "Used in" -->


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`strategy_parameters`
</td>
<td>
A dictionary containing the different
strategy parameters that modify the behavior of a strategy:

```python
# Example parameters of a EMA-based Golden Cross strategy
"strategy_parameters": {
"fast_ema_period": 50,
"slow_ema_period": 200,
}
```
</td>
</tr><tr>
<td>
`initial_balance`
</td>
<td>
Sets the initial balance of the backtester.
</td>
</tr><tr>
<td>
`initial_balance_currency`
</td>
<td>
Currency unit of the initial balance.
</td>
</tr><tr>
<td>
`shared_balance`
</td>
<td>
If set to `True`, all the traded assets would
share the same balance in the exchange. Otherwise, the
initial balance is divided into parts proportional to each
asset's allocation.
</td>
</tr><tr>
<td>
`trading_exchange`
</td>
<td>
Name of the exchange where the backtester will
simulate the trades of the strategy.
</td>
</tr><tr>
<td>
`starting_timestamp`
</td>
<td>
The starting time of the backtester run.
</td>
</tr><tr>
<td>
`ending_timestamp`
</td>
<td>
The ending time of the backtester run.
</td>
</tr><tr>
<td>
`assets`
</td>
<td>
A list of dictionaries containing the different
asset configurations:

```python
"assets": [
{
"trading_symbol": "ADAZ21",
"trading_timeframe": "4h",
"signal_source_exchange": "binance",
"signal_source_symbol": "ADABTC",
"signal_timeframe": "4h",
"allocation": 9,
},
{
"trading_symbol": "XBTUSD",
"trading_timeframe": "4h",
"signal_source_exchange": "binance",
"signal_source_symbol": "BTCUSDT",
"signal_timeframe": "4h",
"allocation": 91,
}
]
```

See the documentation for `bt.config.AssetConfig` for an explanation
of what the different configuration keys are for.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`strategy_parameters`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`initial_balance`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`initial_balance_currency`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`shared_balance`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`trading_exchange`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`starting_timestamp`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`ending_timestamp`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`assets`
</td>
<td>
Dataclass field
</td>
</tr>
</table>



## Methods

<h3 id="from_dict"><code>from_dict</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L181-L241">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@classmethod</code>
<code>from_dict(
    input_config: dict
) -> BacktesterConfig
</code></pre>

Parse an object into a backtester config instance.

This should be the main entry point of any configuration
parsing. If we need to enable JSON or other configuration
formats, we need to convert them first into Python's dictionary
object and pass it to this function:

```python
# Use a JSON string as an input configuration
Backtester.from_dict(convert_json_to_dict(input_json_config))

# Use a YAML string as an input configuration
Backtester.from_dict(convert_yaml_to_dict(input_yaml_config))

# Use an INI string as an input configuration
Backtester.from_dict(convert_ini_to_dict(input_yaml_config))
```

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Raises</th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
Raised if the input configuration has missing
dictionary keys, has an invalid value (for example the
ending timestamp is older than the starting timestamp),
or if extra unrecognized parameter keys is found in the
input configuration.
</td>
</tr><tr>
<td>
`TypeError`
</td>
<td>
Raised if any of configuration values has the
incorrect data type.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Return</th></tr>
<tr class="alt">
<td colspan="2">
The parsed configuration as a <a href="..\bt\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> instance.
</td>
</tr>

</table>



<h3 id="from_json"><code>from_json</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L160-L179">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@classmethod</code>
<code>from_json(
    input_config: str
) -> BacktesterConfig
</code></pre>

Parse an JSON string into a backtester config instance.

See the documentation for <a href="..\bt\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> for an explanation
of what the required configuration structure is.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Raises</th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
Raised if the input configuration has missing
dictionary keys, has an invalid value (for example the
ending timestamp is older than the starting timestamp),
or if extra unrecognized parameter keys is found in the
input configuration.
</td>
</tr><tr>
<td>
`TypeError`
</td>
<td>
Raised if any of configuration values has the
incorrect data type.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Return</th></tr>
<tr class="alt">
<td colspan="2">
The parsed configuration as a <a href="..\bt\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> instance.
</td>
</tr>

</table>



<h3 id="load"><code>load</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L114-L158">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@classmethod</code>
<code>load(
    input_config: (str | dict | BacktesterConfig)
) -> BacktesterConfig
</code></pre>

Auto-detection and dynamic loading of backtest configuration.

See the documentation for <a href="..\bt\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> for an explanation
of what the required configuration structure is.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Arguments</th></tr>

<tr>
<td>
`input_config`
</td>
<td>
This can be a string JSON input, a dictionary,
or an instance of the <a href="..\bt\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a>.
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
Raised if the input is a string but evaluated
as an invalid JSON.
</td>
</tr><tr>
<td>
`ValueError`
</td>
<td>
Raised if the input configuration has missing
dictionary keys, has an invalid value (for example the
ending timestamp is older than the starting timestamp),
or if extra unrecognized parameter keys is found in the
input configuration.
</td>
</tr><tr>
<td>
`TypeError`
</td>
<td>
Raised if any of configuration values has the
incorrect data type.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;">Return</th></tr>
<tr class="alt">
<td colspan="2">
The parsed configuration.
</td>
</tr>

</table>



<h3 id="postvalidation"><code>postvalidation</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L281-L306">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>postvalidation()
</code></pre>

Applies validation to the parsed configuration.


<h3 id="prevalidation"><code>prevalidation</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L243-L279">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@staticmethod</code>
<code>prevalidation(
    input_config: dict
)
</code></pre>

Applies validation to the input configuration.


<h3 id="__eq__"><code>__eq__</code></h3>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>__eq__(
    other
)
</code></pre>






