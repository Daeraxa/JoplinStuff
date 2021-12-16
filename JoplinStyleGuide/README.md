# Joplin Styleguide

This is in a very early state, the wording is a mess, the CSS is a mess and to be honest everything is a mess. This is a pre-alpha v0.0000001 super mega pre-release version. Please don't shout at me...

This mostly came about from a number of different places:
1. I'm was bored
2. I wanted to pracice some HTML/CSS/SASS stuff
3. I got frustrated constantly trying to inspect every element whilst trying to create a new Joplin theme (also for practice and TBA)
4. The demons in my head told me to do it

The *idea* is that this stems from an interest in UI/UX related stuff stretching back over a number of conversations mostly from around autumn of this year that piqued my interest. Mostly surrounding the idea of design systems and overall Joplin theming ideas.

As a prelude to anything else I thought it worth getting stock of the current theming elements to identify what was common, what is easily addressible etc. etc.

During the process I learnt a lot about the Joplin theming code which explains the change in wording the further down the list you get. *See ##TODO section*

Currently I'm only planning to look at the default "Light" and "Dark" themes as these are the ones that overwhelmingly polled in the [recent poll](https://discourse.joplinapp.org/t/what-colour-theme-do-you-mainly-use/20165) and I think best reflect Joplin's identity.

## To "use"
It is just an HTML file and a CSS file created from the related SASS files, you can ignore the SASS files unless you intend to modify it.

Just double click `styleguide.html` and it should launch.

Don't blame me if your computer goes prompt critical and takes down a large section of your home country. It *shouldn't* but this is why people shouldn't trust me with text editors and gin at the same time.

## TODO
If people are interested I might continue. If they aren't then I might also continue.
- [ ] Actually come up with a cohesive naming scheme for the items
- [ ] Wrap themes in their own sections + add collapsing elements
- [ ] Add a button to change the background colour to show various opacities and display colours in their native theme
- [ ] Go over the themeing `.ts` files again and see if I can reflect the "theming areas" better
- [ ] Add editor syntax highlighting
- [ ] Add iconography
- [ ] Add tyopgraphy
- [ ] Add reusable UI elements
- [ ] Fix the responsive web page (please don't squash it, it gets very sad)
- [x] Drink more gin

## Versions
v0.1
- Initial version taking note of most colours in desktop app + setting basic page layout

v0.2
- Removed initial work to use the default reusable colours from the joplin theme .ts files + organise more sensibly
- Added (preliminary) font section that needs work after more thorough understanding of the source code + behaviour compared to Windows and macOS
