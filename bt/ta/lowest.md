<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.ta.lowest" />
<meta itemprop="path" content="Stable" />
</div>

# bt.ta.lowest

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Lowest value for a given number of bars back.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.ta.lowest(
    series: Sequence[int | float],
    length: int
) -> np.array
</code></pre>



<!-- Placeholder for "Used in" -->


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
Optional parameter. Number of bars (length).
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
Raised if `length` is not a number.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
Lowest value in the series.
</td>
</tr>

</table>

