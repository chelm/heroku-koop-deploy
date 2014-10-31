# Deploy Koop to Heroku 

1. Clone koop 

    ```
    git clone git@github.com:Esri/koop.git
    ```

2. Enter the koop project directory and install some providers

    ```
    cd koop

    # install github 
    npm install https://github.com/chelm/koop-github/tarball/master --save 

    # install gist 
    npm install https://github.com/chelm/koop-gist/tarball/master --save
    ```

3. Reset the git origin to a new Git (you need to make this repo)

    ```
    git remote set-url origin git@github.com:{yourname}/{your-koop--deploy-repo}.git
    git commit -a -m 'commit the changes to the package.json file from step 2'
    git push -u origin master
    ```

4. Create a heroku app

    ```
    heroku create --stack cedar-14
    git push heroku master 
    ```

That's it! Now of course there are probably addition changes you'd want to make to the Koop config/default.json file in order to add things like PostGIS, logging, etc.


