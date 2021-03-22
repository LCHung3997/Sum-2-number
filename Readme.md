How to publish packages to npm (the way the industry does things)
20th mar 2019
It’s simple to publish a package onto npm. There are two steps:

Create your package.
Publish the package.
But publishing packages the way the industry does it? Not so simple. There are more steps. We’ll go through what steps are required, and I’ll show you an easy way to publish and update your package.

Creating your first package
This section is for you if you haven’t published a package to npm before. Feel free to skip to the next section if you’ve published one before.

To publish your first package to npm, you need to go through these steps:

First, you need to have an npm account. Create one here if you don’t have one yet.

Second, you need to login to your npm account through the command line. (You need to have Node and npm installed on your system before you perform this step. Install them here).

To sign in, you use npm login.

npm login
You’ll be prompted to enter your username, password, and email address.

Logging into npm via the command line
Third, you need to create a package. To do so, create a folder somewhere on your computer and navigate to it. The command line version is:

# Creating a folder named how-to-publish-to-npm
mkdir how-to-publish-to-npm

# Navigating into the folder
cd how-to-publish-to-npm
Next, you want to begin the project with the npm init command.

npm init
This command runs you through a few questions and creates a package.json file for you at the end. This package.json file contains the bare necessities you need to publish your project. (Feel free to skip questions that don’t make sense).

Image of the npm init command
The final step is to publish your package with the npm publish command.

npm publish
If the package already exists on npm (because your package has the same name as another package on npm), you won’t be able to publish it. You’ll get an error.


You’ll need to change your package name.

To change your package name, you change the name property in the package.json file. Here, I changed it to publishing-to-npm.

(You can check for naming collisions by doing a search on npm, or through the npm search command).

Changed name property to publishing-to-npm
It’s also a good idea to update the folder name as well for consistency. Here’s the command line equivalent.

# Command to change folder names by moving everything
mv how-to-publish-to-npm publishing-to-npm
Try the publish command again. You should get a success message now.

Successfully published to npm
What to do if every name you came up with is taken up already
This is a common problem since many people create packages on npm. It’s difficult to get the package name you desire sometimes. (It’s like how I can never find a good .com domain).

To combat against this problem, npm lets you publish to a scope. This means you can publish the package under your own username (or npm organization), so you’re free from naming problems.

To publish to a scope, you can either:

Change the name to @username/package-name manually in package.json
Run npm init --scope=username instead of npm init
If your repository has a scope, you need to adjust the publish command slightly:

npm publish --access public