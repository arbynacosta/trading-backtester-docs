<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.ta.bbw" />
<meta itemprop="path" content="Stable" />
</div>

# bt.ta.bbw

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Bollinger Bands Width.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.ta.bbw(
    series: Sequence[int | float],
    length: int,
    mult: (int | float)
) -> np.array
</code></pre>



<!-- Placeholder for "Used in" -->

The Bollinger Band Width is the difference between the upper and
the lower Bollinger Bands divided by the middle band.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`series`
</td>
<td>
Series of values to process.
</td>
</tr><tr>
<td>
`length`
</td>
<td>
Number of bars (length).
</td>
</tr><tr>
<td>
`mult`
</td>
<td>
Standard deviation factor.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Raises</h2></th></tr>

<tr>
<td>
`TypeError`
</td>
<td>
Raised if `length` is not a number or
if `multi` is not a number.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
Bollinger Bands Width.
</td>
</tr>

</table>

