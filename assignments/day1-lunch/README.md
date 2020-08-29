# QBB2020 - Day 1 - Lunch Exercises

## Instructions

The following exercises ask you to improve on the plots that we started during the morning session.  Jupyter Notebooks of these plots can be found [here](https://github.com/bxlab/qbb2020/tree/master/day1/1-morning).

To complete these exercises, first create a new directory `/Users/cmdb/qbb2020-answers/day1-lunch`.  Answer each question below by creating a new Jupyter Notebook for each question.  Be sure to:

- Use Markdown to create section headers and add narrative about things you found confusing, useful, or interesting.
- Annotate each plot with a title, axis labels, legends, etc. as appropriate.
- `git commit` after each question.

Pace yourself to complete all the basic exercises.  If time permits, see if you can improve your answers or attempt the advanced exercises.

## Exercises

1. Modify the introductory plot so that each subplot shares the x- and y-axis scales.

        fig, ax = plt.subplots( nrows=2 )
        ax[0].plot( x, y, '.' )
        ax[1].plot( x2, y2 )
        plt.show()

1. Tidy up the plot of K4 chromosome distributions so that it is easier to understand e.g. plot chromosomes in order.

        fig, ax = plt.subplots()
        ax.bar( chr_k4.index, chr_k4 )
        plt.show()

1. Plot K4, K9, and K27 chromosome distributions on the same plot as subplots.

1. Plot K4, K9, and K27 width distributions on the same plot as subplots.

1. Plot a time course of FBtr0331261 with each sex is a separate series.

## Advanced Exercise

1. Plot K4, K9, and K27 width distributions on a single plot without using subplots.

    - HINT: Some suggestions

        - `np.log2()`
        - `ax.hist( range, density, cumulative, histtype )`

1. Add stage 14 replicates to the time course of FBtr0331261.

    `qbb2020/data/replicates.csv`

1. Create an [MA plot](https://en.wikipedia.org/wiki/MA_plot) for two samples of your choice.

