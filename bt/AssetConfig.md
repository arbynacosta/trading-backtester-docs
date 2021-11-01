<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.AssetConfig" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
</div>

# bt.AssetConfig

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Asset-level configuration. Should always be an element of a list.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.AssetConfig(
    trading_symbol: str,
    trading_timeframe: str,
    signal_source_exchange: str,
    signal_source_symbol: str,
    signal_timeframe: str,
    allocation: float
)
</code></pre>



<!-- Placeholder for "Used in" -->


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`trading_symbol`
</td>
<td>
String symbol of the crypto asset in the
trading exchange.
</td>
</tr><tr>
<td>
`trading_timeframe`
</td>
<td>
Execution timeframe of an asset.
</td>
</tr><tr>
<td>
`signal_source_exchange`
</td>
<td>
String symbol of the crypto asset
in the signal source exchange.
</td>
</tr><tr>
<td>
`signal_source_symbol`
</td>
<td>
Name of the exchange where the backtester
will fetch the OHLCV data from.
</td>
</tr><tr>
<td>
`signal_timeframe`
</td>
<td>
The signal timeframe of an asset.
</td>
</tr><tr>
<td>
`allocation`
</td>
<td>
The percent allocation of an asset. The total of
all the `allocation` values must be equal to 1.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`trading_symbol`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`trading_timeframe`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`signal_source_exchange`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`signal_source_symbol`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`signal_timeframe`
</td>
<td>
Dataclass field
</td>
</tr><tr>
<td>
`allocation`
</td>
<td>
Dataclass field
</td>
</tr>
</table>



## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>__eq__(
    other
)
</code></pre>






