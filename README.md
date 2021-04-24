Mak Photography

Highlights
Easy setup and you get a site of your own for free.
To add new pictures, you need to just upload them. No code changes required.

If you know a tad about tech and love taking pictures this template will help in creating the photographer porfolio. 


Just follow the below steps and your website would be live in no time:

Fork this repo by hitting the Fork button at the top right corner.
Enable github pages from the repo settings.
Upload your pictures to images/fulls and images/thumbs directory. You can do that on github.com itself or you can clone and push the images to your repo.
Add your own custom domain in CNAME file or just remove the file if you don't own a domain and use the default domain that github provides ([yourusername].github.io/).
Update baseurl field in _config.yml file with whatever domain you used in step 4.
And that's it, your website is set. To view, go to photography.rampatra.com (or whatever you have in the CNAME file) and if you don't have one, you can go to [yourusername].github.io/images
And, of course, you don't want my name at the bottom to show up. You can change it in _config.yml file as well as few other settings like your google analytics, etc.

ProTips
I have made this as an npm package with gulp to automate image resizing and thumbnail generation. So if you're lazy like me then you can just do the following before you push your images to github.

Fork and then clone the project to your computer
Go inside the project $ cd fotokurious
Install all dependencies by $ npm install
Copy all your pictures (possibly jpg, the largest size available, straight from your camera) and put it inside images directory
Push your changes to github.com by $ git add --all and $ git commit -m "a nice commit message" and then finally $ git push origin master
Contact Form
You can make the contact form work without the need of any server-side code. Just follow this article on github which uses a simple google script to send emails or to upload to a google spreadsheet when someone submits the form.
