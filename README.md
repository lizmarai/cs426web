STEP 1. To initialize a github website with your website code:

First, make sure the machine you are working on has the correct github sshkey: ssh-keygen cd .ssh ls less id_rsa.pub then paste into this file the github sshkey for your github account

Then using the github website make a new repository/project under github and land on the Quick setup with SSH instructions.

On the local machine make a new directory foobar/ and cd to it.

git clone git@github.com:lizmarai/cs426web.git (or whatever the
pathway listed under Quick setup says under ssh).

To bypass future authentification issues:
git remote set-url origin git@github.com:lizmarai/cs426web.git

cp -R all files to foobar ( cp -R ../Downloads/cs426_webpage-main/* cs426/)

cd cs426

cp -R _site docs

git add -f *

git commit -m "first"

git push

STEP 2: Make the website visible Go to Settings for that new project, Pages, then Deploy from Branch, then main/ /docs

STEP 3: Modify the website git config pull.rebase false

git pull

; check the website builds correctly in your terminal: npm start & (the version displayed will be based on the _site files that you build through this command)

copy the _site files to the docs/ folder then git add -f *, git commit, and git push

This is the source code for Prof. Jakob Eriksson's personal webpage, viewable at http://www.cs.uic.edu/~jakob. Feel free to fork this repo to make your own UIC-themed webpage.

To use it, first install node. On a mac, that would be brew install node. On linux, apt-get install nodejs npm.

Then install the static site generator 11ty and the CSS framework tailwind. npm install -D @11ty/eleventy tailwindcss@latest

To use this as a template, start by updatin the settings in _data/defaults.json' to reflect your name, title and a suitable portrait. Delete the contents of 'photos/' and add some of your own. Use landscape oriented photos of high resolution, and with your face fairly prominent and centered. Then, simply edit home.md, projects.mdandnews.md` with your own content, and you're good to go.

To try it out, run npm start in the main folder, and open your website in a browser using the URL localhost:8080. The Makefile contains a handy target for uploading your site to your Computer Science department WWW folder. Works for me, but your YMMV as that's a pretty outdated system.

CS529 Website – Updated Instructions (For future reference)
This website is built with Eleventy (11ty) and Tailwind CSS and is deployed using GitHub Pages. The live site is served from the docs/ folder.

Requirements
Node.js 18 (LTS) is required. Using nvm is recommended.

nvm install v20.17.0
nvm use v20.17.0
One-time setup (first time on a machine)
git clone https://github.com/lizmarai/cs529web.git
cd cs529web
npm install
How to update the website
1. Pull the latest changes
git pull
2. Edit content
Edit Markdown files such as gallery.md, home.md, or projects.md.

Add images to the _site/photos/ folder.

When referencing images, use absolute paths like: src="../photos/fall-2025/example.png"


3. Preview locally (recommended)
npm start

Open a browser and go to:

http://localhost:8081

Stop the server with Ctrl+C when finished.

4. Build the site
npm run build

This generates the website into the _site/ folder.

5. Publish to GitHub Pages
Copy the generated files and folder from _site/ into the docs/ folder:

cp -R _site/. docs/

6. Commit and push changes
git add -A
git commit -m "Update website"
git push
View the live site
After about 30–60 seconds, the website will be available at:

https://lizmarai.github.io/cs426web/

Quick checklist
git pull
(edit markdown files and photos)
npm run build
cp -R \_site/\* docs/
git add -A
git commit -m "Update"
git push
Do NOT edit the _site/ folder directly except for adding images or videos. It is always regenerated.



---------------------------
This is the source code for the cs426 website.

To use it, first install node. On a mac, that would be 
`brew install node`. On linux, `apt-get install nodejs npm`. 

Then install the static site generator 11ty and the CSS framework tailwind. 
`npm install -D @11ty/eleventy tailwindcss@latest`

To use this as a template, start by updatin the settings in `_data/defaults.json' to reflect your name, title and a suitable portrait. Delete the contents of 'photos/' and add some of your own. Use landscape oriented photos of high resolution, and with your face fairly prominent and centered. Then, simply edit `home.md`, `projects.md` and `news.md` with your own content, and you're good to go.

To try it out, run `npm start` in the main folder, and open your website in a browser using the URL `localhost:8080`. 
The `Makefile` contains a handy target for uploading your site to your Computer Science department `WWW` folder. Works for me, but your YMMV as that's a pretty outdated system.
