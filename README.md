# Hosting a Resume on GitHub Pages

---

## Purpose
This README exists to explain how to host a resume on GitHub pages, while also demonstrating principles from **Andrew Etter's** book _Modern Techinical Writing_.<br>


## Prerequisites
This README assumes that you have:
- An understanding of how to navigate your files from the command line
- A resume formatted in markdown
- A text editor
- A GitHub account
- A GitHub personal access token
- Git installed on your computer
- Jekyll installed on your computer



If your require help with any of the above, see the [More Resources](#more-resources) section.

<br>


## Instructions

>### Outcome
> After completing the steps in this README you will be able to host a resume on GitHub pages, using markdown and Jekyll. Here is an example of what your final product may look like:
>
>![resumeGif][rGif]
>
><br>
>
>### 1. Create Static Site with Jekyll
> Now we will use Jekyll to generate a static site, which will have some default content and use the _minima_ theme. The book _Modern Technical Writing_ mentions that Jekyll is currently the most popular static site generator, which is why we will be using it.
>- Open the terminal
>- Navigate to the folder you want to create your site in
>- Enter the following command, replacing _site-name_ with the name you want to give your static site
>```
> jekyll new site-name
>```
>> _**Note**: This will use Jekyll to create a default static site located in a folder called_ **site-name** _in the current folder_
>- Navigate to the newly created folder for your site
>- Enter the following to ensure everything was installed properly
>```
> bundle add webrick
>```
>> _**Note**: If there is an error and the gem was already added, then just continue on_
>- Enter the following to build and locally host your site
>```
> bundle exec jekyll serve
>```
>>_**Note**: By entering the server address in a browser, you can view the default site that was created_
>
><br>
>
>### 2. Format Resume for Static Site
> While your resume is formatted in markdown, it requires an additional step before it can be added to your static site. Jekyll requires all pages have _front matter_ that tells the page how to format and display your content. The front matter is used by the static site's theme to customize the site and display your content. In his book _Modern Technical Writing_, **Andrew Etter** emphasizes the importance of themes and customization in making your work stand out from the rest. There will be a link to a tutorial on Jekyll themes in the _[More Resources](#more-resources)_ section.
>- Open your markdown resume in an editor
>- Enter the following at the very top, above all other text:
>```
> ---
> layout: default
> ---
>```
>> _**Note**: This will add the default layout to your resume. Almost all Jekyll themes have a default layout_
>- Save your changes
>
><br>
>
>### 3. Add Resume to Static Site
> The next step is to turn the default static site into one for your resume. As **Andrew Etter** mentioned in his book, static sites are fast, simple, portable, and secure. For those reasons they are an ideal place to host a resume.
>- Open your resume in an editor
>- Save your resume as the following, in your static site's root folder:
>```
> index.markdown
>```
>> _**Note**: This will overwrite the original_ **index.markdown** _file. This is not an error._
>- Delete the following from your static site's root folder:
>   - _about.markdown_ file
>   - __posts_ folder
>> _**Note**: These are not needed for your resume site._
>- Navigate to your static site's folder in the terminal
>- Enter the following command
>```
> bundle exec jekyll serve
>```
>> _**Note**:This will rebuild your static site with all changes made. You can go to the server address to view your completed resume site._
>
><br>
>
>### 4. Create New Repository
> Now we need to create the GitHub repository that will host your static site. In _Modern Technical Writing_, **Andrew Etter** notes that while a version control system, such as git, may be overkill for what we're using it for, it has better performance than other options, allows for offline work and shows any possible employers that you are comfortable of using modern tools in your work.
>- Navigate to _[github.com][ghLink]_ in a browser
>- Sign-in to your GitHub account
>- Click your profile picture at the top right of the screen
>- Navigate to _Your repositories_
>- Press the _New_ button and create a new repository
>- Name your new repository the following, replacing _name_ with your username
>```
> name.github.io
>```
>- Click to make your repository public
>- Make sure the _add a README_ choice is **NOT** checked
>- Press the create repository button
>- Write down or save the url to your repository
>
><br>
>
>### 5. Add Resume Site to GitHub Pages
> Next we will upload our site to the GitHub repository we created. With resume on a website we can view and edit our site at any time, making it much easier to keep up to date. This is one of the reasons **Andrew Etter** recommends keeping your work on a website in his book.
>- Open your static site's __config.yml_ file in a text editor
>- Locate the line that says:
>```
> url: ""
>```
>- Change the line to the following, replacing _repo-name_ to the name of your created repository:
>```
> url: "repo-name"
>```
>>_**NOTE**: Make sure that the line_ **baseurl:** _Has an empty string. If it doesn't your resume may not show up properly. You can also change the_ **title** _and_ **description** _to be whatever you want. I went with my repository name for a title, and "My Resume" for the description._
>- Save __config.yml_
>- Open the terminal
>- Navigate to your static site's file folder in the terminal
>- Initialize the local repository by entering:
>```
> git init
>```
>- Create a GitHub pages branch of your repository by entering:
>```
> git checkout -b gh-pages
>```
>- Add all files to the branch using the command:
>```
> git add .
>```
>- Commit the changes to the repository by entering:
>```
> git commit -m "initial commit"
>```
>- Enter the command, replacing _repo-url_ with the url to your GitHub repository.
>```
> git remote add origin <repo-url>
>```
>>_**NOTE**: This will link your local repository to your remote repository._
>- Push the local committed files to your remote repository by entering:
>```
> git push origin gh-pages
>```
>- Enter your GitHub username when prompted
>- Enter your **personal access token** when prompted for a password
>- Enter your repository url in a browser to view your resume website
>>_**NOTE**: It may take a minute or two to show up._
>
><br>
>
>### 6. Edit Resume on GitHub Pages
> Unlike with PDFs, with a resume published on a static site, you can edit your resume at any time from any computer. That is one of the reasons **Andrew Etter** suggests using websites in place of PDFs.
>- Sign-in to your _[GitHub][ghLink]_ account in any browser
>- Go to the repository holding your resume
>- Click on the _index.markdown_ file
>- Click the **pencil** icon to edit your resume
>- Make any edits you want
>- Press the _Commit changes_ button at the bottom of the screen
>- View your updated resume by entering the url in a browser. You're Done!
<br>
<br>


## More Resources
- **Andrew Etter's** _[Modern Technical Writing][EtterLink]_
- _[Github][ghLink]_
- Command Line Tutorials for _[Windows][winLink], [Mac][macLink],_ and _[Linux][linLink]_
- [Markdown Tutorial][mdTutorial]
- _[Markdown Editors][mdEditors]_
- GitHub _[Account Tutorial][ghAccount]_
- GitHub _[Personal Access Token][ghToken]_
- _[Installing Git][gitInstall]_
- _[Text Editors][tEditors]_
- _[Jekyll Installation][jInstall]_
- _[Jekyll Themes Tutorial][jkThemes]_

## Authors and Acknowledgements

- Tanisha Turner
- Group Members:
  - Jishan Arora 
  - Xing Zhou 
  - Joseph Godard 
  - Adam Donen 
- _[Modernist Theme][ghTheme]_ Authors: 
  -_[Steve Smith][ghSS]_
  - _[Ben Balter][ghBB]_ 
  - _[Parker Moore][ghPM]_
  - _[Tekaoh][ghTekaoh]_
  - _[Slavik Nychkalo][ghSN]_

## FAQs
>#### Why is Markdown better than a word processor?
> Markdown is better than a word processor because it is easy to learn, easy to customize, and easy to read for both humans and machines. It can also be written and edited in almost any editor, on any type of system, making it very portable.
>#### Why is my resume not showing up?
> Your resume may not be showing up for a few different reasons.
>1. You may just need to wait. Sometimes it takes a minute or two for your resume to show up on the website.
>2. Your __config.yml_ file may have the wrong urls entered. Make sure that the  _baseurl:_ has an empty string after it, and the _url:_ line has the name of your repository. For example: <br>
![urlExample][urlEx]
>3. Make sure that your markdown resume has the required _front matter_ and that they layout in your _front matter_ is supported by your theme.

<br>

[Back To Top](#hosting-a-resume-on-gitHub-pages)

[rGif]: ./resume.gif
[doneGif]: ./done.gif
[urlEx]: ./urlEx.png


[ghLink]: https://www.github.com
[EtterLink]: https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS/ref=sr_1_1?dchild=1&keywords=modern+technical+writing&qid=1635879424&sr=8-1
[winLink]: https://www.computerhope.com/issues/chusedos.htm
[macLink]: https://computers.tutsplus.com/tutorials/navigating-the-terminal-a-gentle-introduction--mac-3855
[linLink]:https://www.digitalocean.com/community/tutorials/basic-linux-navigation-and-file-management
[mdTutorial]: https://www.markdowntutorial.com/
[ghAccount]: https://www.wikihow.com/Create-an-Account-on-GitHub
[ghToken]: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
[GitInstall]: https://github.com/git-guides/install-git
[mdEditors]: https://www.oberlo.ca/blog/markdown-editors
[tEditors]: https://www.techradar.com/best/best-text-editors
[jInstall]: https://jekyllrb.com/docs/installation/
[jkThemes]: https://jekyllrb.com/docs/themes/

[ghTheme]: https://github.com/pages-themes/modernist
[ghSS]: https://github.com/orderedlist
[ghBB]: https://github.com/benbalter
[ghPM]: https://github.com/parkr
[ghTekaoh]: https://github.com/Tekaoh
[ghSN]: https://github.com/gebeto