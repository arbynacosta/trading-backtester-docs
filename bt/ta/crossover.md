<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="bt.ta.crossover" />
<meta itemprop="path" content="Stable" />
</div>

# bt.ta.crossover

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Checks if `series_1` crossed over `series_2`.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>bt.ta.crossover(
    series_1: Sequence[int | float],
    series_2: Sequence[int | float]
) -> bool
</code></pre>



<!-- Placeholder for "Used in" -->

The `series_1`-series is defined as having crossed over
`series_2`-series if, on index-0, the value of `series_1` is
greater than the value of `series_2`, and on index-1, the value
of `series_1` was less than the value of `series_2`.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`series_1`
</td>
<td>
First data series.
</td>
</tr><tr>
<td>
`series_2`
</td>
<td>
Second data series.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2" style="text-align: left;"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
`True` if `series_1` crossed over `series_2` otherwise `False`.
</td>
</tr>

</table>

