### My Notes

My personal notes deployed as blogs! <br>
Find it out here - https://rudradesai.in/mynotes

#### Setup
- First, Install hugo : https://gohugo.io/getting-started/installing/
- Now, clone this repository with --recurse-submodules flag.
    - `git clone --recurse-submodules <url>`
- You are ready to use this repo.


#### Usage
- Go to the root directory and use the following commands
    - `hugo server` will start the hugo server on port 1313
    - `hugo server -D` will start the server with Drafts.
    - `hugo new <path>` will add the corresponding file to the content directory.
        - Ex: `hugo new about/about-us.md` created the only visible page now

- Important pages
    - `_index.md` Page under any content folder is used for describing the main page.
    - All other pages are children pages.
    - Nested folders can also be added.

#### Contributing
- Create a new branch before starting to contribute.
    - `git checkout -b rudra` will create a new branch rudra from master.
- Now add whatever there is to add in this branch and create a pull request.
- After all the green ticks from the reviewers and the build tests, your pr will be merged. 

#### Deploy
- Hugo websites can be deployed using netlify as well as ghpages.
- See the theme page to find out more.