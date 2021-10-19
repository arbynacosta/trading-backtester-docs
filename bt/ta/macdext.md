<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.ta.macdext" />
<meta itemprop="path" content="Stable" />
</div>

# bt.ta.macdext

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



MACDEXT(real[, fastperiod=?, fastmatype=?, slowperiod=?, slowmatype=?, signalperiod=?, signalmatype=?])

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.ta.macdext()
</code></pre>



<!-- Placeholder for "Used in" -->

MACD with controllable MA type (Momentum Indicators)

#### Inputs:


* <b>`real`</b>: (any ndarray)


#### Parameters:


* <b>`fastperiod`</b>: 12
* <b>`fastmatype`</b>: 0
* <b>`slowperiod`</b>: 26
* <b>`slowmatype`</b>: 0
* <b>`signalperiod`</b>: 9
* <b>`signalmatype`</b>: 0


#### Outputs:

macd
macdsignal
macdhist
