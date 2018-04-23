Think outside of the Box

I am Philipp Hinrichsen

Twitter: @Sp3c1
Github: Poltergeist

- we use Technologies each day
  - the same way
    - we should reconsider

for example Git
  -we write git commit messages
  - this could be a journal
    - Like a Blog? wait ... this is awesome...

```bash
bash-3.2$ vi ~/projects/jsunconf2018/toob.md
bash-3.2$ cd ~/projects/journal/
bash-3.2$ git log
commit 7c30509e2973c420a776265f5de24bda4ef36c0e (HEAD -> master, origin/master)
Author: Poltergeist <philipph@mesosphere.io>
Date:   Wed Apr 18 14:01:44 2018 +0200

    Bookmark: react child components

    This is a good article about react childrens and how to handle them [react children deep
    dive](https://mxstbr.blog/2017/02/react-children-deepdive/)

commit 70cd8cb758318a8fde4217306c98e3b85b66ed10
Author: Poltergeist <philipph@mesosphere.io>
Date:   Mon Apr 16 10:16:46 2018 +0200

    Bookmark: react-spring

    Helping react-motion and animated to become best friends. [react Spring](https://github.com/drcmda/react-spring)

commit 6434277534e3b05c1f8ab0dc49904ba244f2a430
Author: Poltergeist <philipph@mesosphere.io>
Date:   Sun Apr 15 00:21:51 2018 +0200

    --exclude: add jekyll theme

commit b645ae729620d7df2a71541aaf813786c23c1b3c
Author: Poltergeist <philipph@mesosphere.io>
Date:   Sun Apr 15 00:18:12 2018 +0200

    Log: Today I Build

    Today I have build a Journal system based on git commit massages. After I did an empty commit I can
    `git log` the massages into a mark down file which I deploy on github. I have a commit type for
    excluding commits so that I can filter these out. This works actually pretty good. So now I have a
    Journal which I can use without opening a browser :-) This is pretty cool.

commit f3d28ca63aec6e5aa95e8003c1bdf50af594ace4
Author: Poltergeist <philipph@mesosphere.io>
Date:   Sun Apr 15 00:11:28 2018 +0200

    --exclude: build

    add build script

commit 12357330272f86b6a19fa2374e0d53eac7cc1392
Author: Poltergeist <philipph@mesosphere.io>
Date:   Sat Apr 14 23:05:33 2018 +0200

    Bookmark: Blueprint react JS component library

    [blueprint](http://blueprintjs.com/) - react component library is a great example of a typescript
    component library. Using a Monorepo architecture.

commit 8b5816bdea7d0b738e71c5c3b52ad4a303d6f5d7
Author: Poltergeist <philipph@mesosphere.io>
bash-3.2$ git log --oneline
7c30509 (HEAD -> master, origin/master) Bookmark: react child components
70cd8cb Bookmark: react-spring
6434277 --exclude: add jekyll theme
b645ae7 Log: Today I Build
f3d28ca --exclude: build
1235733 Bookmark: Blueprint react JS component library
8b5816b Bookmark
456e14f --exclude(add commitizen config):
2401e6f --exclude: INIT
bash-3.2$ cat package.json | jq .scripts
{
  "test": "echo \"Error: no test specified\" && exit 1",
  "prebuild": "rimraf dist && mkdir dist && echo \"# Journal\n\n\" > dist/index.md",
  "build": "git log --format=\"## %s - %ai%n%n %b %n\" --grep=\"--exclude\" --invert-grep >> dist/index.md",
  "postbuild": "cp ./_config.yml ./dist/ && gh-pages -d dist"
}
bash-3.2$ git cz --allow-empty
/Users/sp3c1/projects/journal
/Users/sp3c1/projects/journal
cz-cli@2.9.6, journal-log@0.0.0-semantically-released.0


Line 1 will be cropped at 100 characters. All other lines will be wrapped after 100 characters.

? Select the type of change that you're committing: Bookmark:  bookmark a link
? Write a short, imperative tense description of the change:
 JSunconf is an awesome conference
? Provide a longer description of the change: (press enter to skip)
 And this might be the link for the next awesome jsunconf [2019.jsunconf.eu](https://2019.jsunconf.eu)


bash-3.2$ exit
exit
bash-3.2$ pwd
/Users/sp3c1/projects/journal
bash-3.2$ npm run build

> journal@0.1.0 prebuild /Users/sp3c1/projects/journal
> rimraf dist && mkdir dist && echo "# Journal

" > dist/index.md


> journal@0.1.0 build /Users/sp3c1/projects/journal
> git log --format="## %s - %ai%n%n %b %n" --grep="--exclude" --invert-grep >> dist/index.md


> journal@0.1.0 postbuild /Users/sp3c1/projects/journal
> cp ./_config.yml ./dist/ && gh-pages -d dist -o https

Published
bash-3.2$ git browse
git: 'browse' is not a git command. See 'git --help'.

The most similar command is
	web--browse
bash-3.2$ exit
exit
bash-3.2$ exit
bash-3.2$ exit
```
