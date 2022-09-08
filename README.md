\[_This repository was generated [from a Hugo GitHub Pages template](https://github.com/jlumbroso/hugo-github-bearblog-template), that allows you to [create your own website in 1-click, and host it for free, forever!](https://github.com/jlumbroso/hugo-github-bearblog-template/generate)_\]

# Princeton CS Intro Lab Webpage

This repository contains Princeton University's Department of Computer Science _Intro Lab_ webpage, which is hosted at [`introlab.cs.princeton.edu`](https://introlab.cs.princeton.edu). The website is compiled using [Hugo](https://gohugo.io/), is hosted on [GitHub Pages](https://pages.github.com/), and is automatically updated whenever a new commit is pushed to the `main` branch using GitHub Actions.

## Contributing

All content is written using Markdown (see [cheat sheet](https://www.markdownguide.org/cheat-sheet/) or [more detailed explanations](https://www.markdownguide.org/)).

To edit the landing page, simply commit and push a change to the file `content/_index.md`. This can be done through `git` or [directly online, on GitHub](https://github.com/PrincetonCS-UCA/intro-lab-website/edit/main/content/_index.md). Note that if you are not part of the management team, you might need to first *fork* the repository to your own account before making a change — and then make a pull request to suggest the change be made. (Or you could apply to become a member of the management team! 😁)

## .htaccess from old website

The old website was hosted at `labta.cs.princeton.edu`, and is configured to still exist with the following redirections:

```apache
Redirect 301 /index.html "https://introlab.cs.princeton.edu/index.html"
Redirect 301 /studentguide.html "https://introlab.cs.princeton.edu/how-to-effectively-use-intro-lab-tas/index.html"
Redirect 301 /info.html "https://introlab.cs.princeton.edu/information-about-becoming-an-intro-lab-ta/index.html"
```