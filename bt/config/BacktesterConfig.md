<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.config.BacktesterConfig" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_dict"/>
<meta itemprop="property" content="from_json"/>
<meta itemprop="property" content="load"/>
</div>

# bt.config.BacktesterConfig

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Class representation of a backtester configuration.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Main aliases</b>
<p>`bt.BacktesterConfig`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.config.BacktesterConfig(
    strategy_parameters: AttrDict,
    initial_balance: float,
    initial_balance_currency: str,
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
"percent_allocation": 9,
},
{
"trading_symbol": "XBTUSD",
"trading_timeframe": "4h",
"signal_source_exchange": "binance",
"signal_source_symbol": "BTCUSDT",
"signal_timeframe": "4h",
"percent_allocation": 91,
}
]
```

See the documentation for <a href="..\..\bt\config\AssetConfig.md"><code>bt.config.AssetConfig</code></a> for an explanation
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

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L173-L229">View source</a>

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
The parsed configuration as a <a href="..\..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> instance.
</td>
</tr>

</table>



<h3 id="from_json"><code>from_json</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L152-L171">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@classmethod</code>
<code>from_json(
    input_config: str
) -> BacktesterConfig
</code></pre>

Parse an JSON string into a backtester config instance.

See the documentation for <a href="..\..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> for an explanation
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
The parsed configuration as a <a href="..\..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> instance.
</td>
</tr>

</table>



<h3 id="load"><code>load</code></h3>

<a target="_blank" href="https://github.com/tensorflow/docs/tree/master/tools/tensorflow_docs\config.py#L110-L150">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>@classmethod</code>
<code>load(
    input_config: (str | dict | BacktesterConfig)
) -> BacktesterConfig
</code></pre>

Auto-detection and dynamic loading of configuration.

See the documentation for <a href="..\..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> for an explanation
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
The parsed configuration as a <a href="..\..\bt\config\BacktesterConfig.md"><code>bt.BacktesterConfig</code></a> instance.
</td>
</tr>

</table>



<h3 id="__eq__"><code>__eq__</code></h3>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>__eq__(
    other
)
</code></pre>






