Main branch will be ```develop```.

Procedure goes like this:

Create a new branch from ```develop```

After making changes to mkdocs md files.

We do ```mkdocs build```

We add to commit all the files changed and generated and push.

Always we'll make PR against -> ```main```.

After PR gets merged to main. Netlify will take the build folder (site) and publish the site.