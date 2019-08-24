The
<a href = "https://statsbomb.com/2019/07/a-sneak-peak-at-iq-tactics-a-brief-history-of-radials-sonars-wagon-wheels-in-soccer/">Statsbomb
article on passing sonars</a> prominently featured the below template -

![](https://i2.wp.com/statsbomb.com/wp-content/uploads/2019/07/Pass_Sonar_LionelMessi_La-Liga_2018_2019.png?resize=1024%2C907&ssl=1)

### I have three issues with this design

-   The spoke of the wheel is able to communicate only one aggregated
    value for the length of the passes and the accuracy of the passes.
    By combining all the passes that were made in that angle bucket into
    one accuracy and one length number we lose out on a more granular
    view of the passes.

-   There is no indication of how many passes belong to a particular
    sonar or spoke. Spokes with very few passes would visually get as
    much attention as spokes with many passes which could lead to
    misinterpreting the typical length or the typical success percent.

-   Note how the spoke expands in width as it moves farther from the
    centre. This means that the longer the pass, the more area is
    covered by the respective spoke. For a short pass to belong to a
    particular spoke, it would have to fall in a far smaller region than
    for a long pass to belong to the same spoke. When looking at a sonar
    without consciously being aware of it, This may lead to misleading
    inferences.

### With the design below, I try to solve these problems with some more minor enhancements

-   Think of the chart as a bunch of concentric rings. Each ring
    captures passes falling within a particular range of lengths. The
    rings are equally spaced so the increase in range from ring 1 to
    ring 2 is the same as the increase in range from any ring n to ring
    n + 1.

-   The radius of the circle in the background of each sonar is
    proportional to the length of the pitch. You can use that as a
    reference to get an idea of how long a pass actually

-   Each block in the ring captures passes of the respective lengths in
    a paritcular range of direction - specifically all angles
    originating from the centre of the circles and passing between the
    left edge and right edge of the block.

-   The blocks have been calculated in such a way to cover approximately
    the same sized area of the pitch as any other block, which is why
    each block spans a lesser part of the circumference on passes of
    longer lengths compared to the part of the circumference it covers
    on passes of shorter lengths.

-   The thickness of each block in the ring is proportional to the
    number of passes of that length and angle. ( It’s actuallly
    proportional to the square root of the number of passes, if I make
    it proportional then the blocks with few passes become too small to
    be visible. This is an acceptable workaround to me since the idea is
    to give an indication of the number of passes, and not really expect
    people to be able to infer the number of passes. )

-   The colour of each block is proportional to the success percent of
    the passes associated with that block, going from red to dark green
    for 0% to 100%

-   In the pitch break up, each sonar is constructed the same way as the
    above but captures only passes originating from that area.

### How the problems get solved

-   Since we removed the spoke concept and implemented rings and blocks
    instead, we have some break up between passes of various length.
    Given that passes of different lengths are represented differently,
    we also get a better idea of accuracies across different pass
    lengths.

-   Each block gives a visual cue about the number of passes falling in
    that length, direction combination.

-   Each block is calculated in such a way that it covers approximately
    the same area as all other blocks which allows us to compare blocks
    and get an idea of which parts of the pitch received more passes and
    which parts received less.

### Passing Cobblestone Circles

… is what come to mind but it’s unlikely to be a name that catches on so
we’re going to have to stick to sonar.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Paver_Blocks_Exterior_Circular_3008px.jpg/1920px-Paver_Blocks_Exterior_Circular_3008px.jpg)

( opening images in a new tab by themselves might be a better view )

<img src="./plotOverallSonar.png" width="1500" /><img src="./plotPitchBreakupSonar.png" width="1500" /><img src="./plotPlayerBreakupSonar.png" width="1500" />
