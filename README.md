# OGC Testbed-12 KO EOX-GeoSolutions Presentation

Presentation at the [OGC Testbed 12 Kick-Off]().

## Running presentation

Point your browser to the [online presentation](http://schpidi.github.io/ogc-testbed12-ko)
or serve it locally.

```bash
git clone https://github.com/Schpidi/ogc-testbed12-ko.git
cd ogc-testbed12-ko
git submodule init
git submodule update
npm install
grunt serve
```

## Creating presentation

After creating a new repository at GitHub without initializing it run the
following.

```bash
mkdir presentation
cd presentation
git init
git checkout -b gh-pages
git remote add origin git@github.com:Schpidi/ogc-testbed12-ko.git
git submodule add https://github.com/Schpidi/reveal.js.git
cd reveal.js/
git checkout eox
cd ..
git add reveal.js/

ln -s reveal.js/Gruntfile.js Gruntfile.js
ln -s reveal.js/package.json package.json
npm install

echo "node_modules/" >> .gitignore
git add Gruntfile.js package.json .gitignore
git commit -m "Adding reveal.js."

cp reveal.js/index.html .
# Edit index.html to your liking
git commit index.html -m "Adding presentation."

vi README.md
vi LICENSE
git add README.md LICENSE
git commit -m "Adding readme and license."

git push -u origin gh-pages
```
