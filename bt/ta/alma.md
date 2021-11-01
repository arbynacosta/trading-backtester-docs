<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.ta.alma" />
<meta itemprop="path" content="Stable" />
</div>

# bt.ta.alma

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Arnaud Legoux Moving Average.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.ta.alma(
    series: Sequence[int | float],
    length: int,
    offset: (int | float),
    sigma: (int | float),
    floor: bool = False
) -> np.array
</code></pre>



<!-- Placeholder for "Used in" -->

Uses Gaussian distribution as weights for moving average.

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
`offset`
</td>
<td>
Controls tradeoff between smoothness (closer to 1) and
responsiveness (closer to 0).
</td>
</tr><tr>
<td>
`sigma`
</td>
<td>
Changes the smoothness of ALMA. The larger sigma the
smoother ALMA.
</td>
</tr><tr>
<td>
`floor`
</td>
<td>
An optional parameter. Specifies whether the offset
calculation is floored before ALMA is calculated. Default
value is `False`.
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
Raised if `length` is not a number, or
if `multi` is not a number, or `sigma` is not a number.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
Arnaud Legoux Moving Average.
</td>
</tr>

</table>

