# Vagrant project for deploying Haskell to Heroku

The project puts together the important parts of deploying Haskell to
Heroku:

* Ubuntu 10.04
* GHC 7.0.4
* Haskell Platform 2011.4.0.0
* Heroku Toolbelt

After running `vagrant up`, you should be able to run `vagrant
ssh`. After you're in, you should be able to compile and deploy your
project:

    git clone git@bitbucket.org:puffnfresh/my-haskell-project.git
    cd my-haskell-project
    git checkout -b deploy
    cabal update
    cabal install
    git add -f dist/build/my-haskell-project/my-haskell-project
    git commit -m "Deploy `date`"
    git remote add heroku git@heroku.com:my-haskell-project.git
    git push -f heroku deploy:master
