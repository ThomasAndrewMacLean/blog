I made a small demo website that show's how you can style a list of cards and make it snap into space.

The demo can be found [here](https://thomasandrewmaclean.github.io/snappy-scrolly-demo/).

It uses checkboxes to add features one-by-one and every checkbox has a data-info attribute with some information on whats happening in that step.
On hover over the checkbox we use the ::after element with fixed position and content from the data-attribute to show that information on screen.

The adding of features by checking the boxes is also done with only CSS, and uses the :has feature a lot.
