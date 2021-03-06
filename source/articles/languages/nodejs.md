---
sidebar_current: "languages-nodejs"
---

# Node.js

Below are several guides on getting started with Node.js and wercker.

* [Getting Started with Express and Mocha](/articles/languages/nodejs/getting-started-express-and-mocha.html)
* [Test-Driven-Development with Express, MongoDB and Mongoose](/articles/languages/nodejs/tdd-with-mongoose.html)

## Guides

Wercker supports [node.js](http://nodejs.org). The default [wercker.yml](/articles/werckeryml) file for node.js is the following:

    box: wercker/nodejs
    # Build definition
    build:
      # The steps that will be executed on build
      steps:
        # A step that executes `npm install` command
        - npm-install
        # A step that executes `npm test` command
        - npm-test

        # A custom script step, name value is used in the UI
        # and the code value contains the command that get executed
        - script:
            name: echo nodejs information
            code: |
              echo "node version $(node -v) running"
              echo "npm version $(npm -v) running"


At the top you see the 'box' definition that states we want the 'wercker/nodejs' box. This box includes node.js version 0.8.24. If you want to run any other version of node.js feel free to fork this [box definition](https://github.com/wercker/box-nodejs).

Next, there is a 'build' clause, this defines your build pipeline on wercker. There are two types of build steps:

#### predefined buildsteps
Predefined buildsteps such as npm-install in the wercker.yml above. This command wraps the `npm install' command that installs dependencies from the *package.json*.

#### custom buildsteps
Custom build steps, which are basically bash scripts defined via the 'script' clause, requiring a 'name' and 'code' section. In the example file above we created a custom build step called 'echo nodejs information' that echos the node and npm versions back to us.

See the [wercker.yml section](/articles/wercker.yml) for more information.

-------

<div class="authorCredits">
    <span class="profile-picture">
        <img src="https://secure.gravatar.com/avatar/d4b19718f9748779d7cf18c6303dc17f?d=identicon&s=192" alt="Micha Hernandez van Leuffen"/>
    </span>
    <ul class="authorCredits">

        <!-- author info -->
        <li class="authorCredits__name">
            <h4>Micha Hernandez van Leuffen</h4>
            <em>
                Micha is cofounder and CEO at wercker.
            </em>
        </li>

        <!-- info -->
        <li>
            <a href="http://beta.wercker.com" target="_blank">
                <i class="icon-company"></i> <em>wercker</em>
            </a>
            <a href="http://twitter.com/mies" target="_blank">
                <i class="icon-twitter"></i>
                <em> mies</em>
            </a>
        </li>

    </ul>
</div>

-------
##### last modified: Sept 7, 2013
-------
