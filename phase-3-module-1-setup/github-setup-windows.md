# Git and GitHub Setup for Windows

GitHub is one of the key collaborative tools that enable teams of developers to
build and maintain web applications using the Git version control system. In
this article, you'll learn more about some of the key features of the Git and
GitHub, as well as set up an account if you do not have one already.

By the end of this article you will be able to:

1. Sign up for a GitHub account and set up a basic user profile
2. Configure GitHub authentication using Git Credential Manager (GCM).
3. Describe how you can leverage your profile throughout the program in order to
   prepare for the job search
4. Identify the main elements of a repository that support collaboration

## Creating a GitHub account

In order to start collaborating on GitHub, you will need to create an account.
If you have already created an account, move onto [Setting up a GitHub profile].

1. Navigate to the [GitHub Homepage] and click on the "Sign up" button in the
   top right-hand corner of the window.
2. Fill out all of the information on the form, and verify that you are a real
   person before clicking "Create account".

## Setting up a GitHub profile

You can think of your GitHub profile as your way of introducing yourself to the
developer world. In this section, you will get started by setting up some basic
elements, but you will revisit this profile as you gain experience, and will
ultimately polish it up before starting your job search.

1. Sign in to your account from the [GitHub Login Page].
2. Navigate to your profile by clicking on the avatar in the top right-hand
   corner of the window. Click on "Your profile".
3. Click on "Edit profile" to create your profile. Fill out the fields and click
   "Save".

Remember, this profile is what other developers will see when they look at your
work. Make sure it shows who you are, but in a professional manner. To see an
example and learn more, check out [About your profile] in GitHub's
documentation.

## Installing Git and Git Credential Manager

If you have already installed Git and GCM, then move onto the
[Use GCM in WSL] section.

Git is a Version Control System, or VCS. It keeps track of a set of files over
time, and is used through the command line.

[Git Credential Manager] is the recommended secrets manager for GitHub
authentication.

Because GitHub allows you to share code with other developers, there needs to be
a way to authenticate to make sure that you are authorized to access or
contribute new code.

Thankfully, git handles this authentication flow automatically. But for GitHub,
there are several options for handling this authentication. These instructions
will walk you through setting up authentication through Git Credential Manager,
which is App Academy's preferred method.

__If you have _never_ configured GitHub authentication before, follow the
instructions below to set up Git Credential Manager. If you already have
authentication set up using a PAT or SSH key, you may continue using that
approach. You can reference this [SSH article] or [PAT article] for
troubleshooting your existing setup if needed.__

1. Navigate to the [Git For Windows] download page.
2. Click on the "Click here to download" hyperlink at the top of the page to
   download and install the latest version.
3. Follow the instructions on the installer to complete the download and
   installation for Git and GCM. Use the configuration options below:
   - On the "Select Components" box, make sure "Windows Explorer Integration" is
     checked, and BOTH checkboxes are checked underneath ("Git Bash Here" and
     "Git GUI here")

     ![Select components][Select components]

   - On the next screen, select "Use Visual Studio Code as Git's default
     editor".

     ![VScode default][VScode default]

   - On the next screen, select "Override the default branch name for new
     repositories". "main" should be in the text box input.

     ![Default branch name][Default branch name]

   - On the next screen, select "Use Git and optional Unix tools from the
     Command Prompt".

     ![Git command line][Git command line]

   - On the next screen, select "Use bundled OpenSSH".
   - On the next screen, select "Use the OpenSSL library".
   - On the next screen, select "Checkout as-is, commit Unix-style line
     endings".

     ![Git checkout Unix line endings][Git checkout Unix line endings]

   - On the next screen, select "Use Windows' default console window".

     ![Window default][Window default]

   - On the next screen, select "Default (fast-forward or merge)".
   - On the next screen, select "Git Credential Manager".
   - On the next screen, select "Enable file system caching"

     ![Enable caching][Enable caching]

   - Then "Install". __Note__: Do not select any of the boxes on the final
     installation page.
3. Open your __Windows PowerShell__ terminal by searching for "PowerShell" in
   the start menu. Then right click on it and select "Run as administrator".

   ![Open PowerShell as Admin][Open PowerShell as Admin]

4. Now, test that you set up Git and GCM properly. Run the following command:

   ```sh
   git clone https://github.com/appacademy/setup-test-gcm.git
   ```

5. You should get prompted by a new Window to enter your GitHub credentials.

   ![GCM-browser-screenshot]

6. Choose "Browser/Device" and click "Sign in with your browser".
7. Enter your GitHub username and password. Upon providing your credentials,
   your terminal should report it's success with the given operation.

### Use GCM in WSL

If you followed the directions for installing Git and GCM for Windows as
outlined above, you will connect the Windows GCM to WSL.

1. Open up your __Ubuntu terminal__ and enter this command to tell your Git in
   WSL where it can locate the Git Credential Manager in your Windows
   environment:

   ```sh
   git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"
   ```

2. You need to configure Git, so run the following command in your Ubuntu
   terminal, but replace "Your Name" with your real name:

   ```sh
   git config --global user.name "Your Name"
   ```

3. Then run the following command, but replace "your@email.com" with your real
   email:

   ```sh
   git config --global user.email your@email.com
   ```

4. Check that Git is installed and configured properly by running the following
   commands into the Ubuntu terminal. You should see your real name and real email
   address printed after the commands:

   ```sh
   git config --global user.name    # your name printed after the command

   git config --global user.email   # your email address printed after the command
   ```

5. Enter the following command in your terminal to specify that your default Git
   branch of any new repository should be called the `main` branch:

   ```shell
   git config --global init.defaultBranch main
   ```

Now, any time you need an authorized Git request, WSL will send a signal out to
GCM on Windows to handle the auth side of things.

## Keeping your garden green

When you go to your GitHub profile page, you will notice a section for the
amount of contributions in the last year. Underneath that, there is a grid of
green squares. The green squares represent all of your coding contributions to
GitHub. Employers use this information to help determine how active you are in
developing your coding abilities. As App Academy students, your job is to
populate this green garden as much as possible during your time here to build
your reputation as a developer!

To ensure that all of your activity shows up on your garden, click on
"Contribution Settings" just above the garden box. Make sure that "Private
Contributions" is checked to make sure that all of your work will be represented
on the chart.

![enable-private-repo-contributions]

## Collaborating on a Repository

In GitHub, you will create a _repository_ for every project you create. The
repository houses all of the code for the project, as well as other important
information such as the license and a _README_ file which describes the project
and shares important information on how to run, and contribute to the project.

![collaboration-workflow-1]

The project repository includes all of the tools needed for the collaborative
workflow described above. You start by cloning the project, or saving it to your
computer, you can then work on the project, and push your updated code back up
to the repository so others can work with it.

[GitHub Homepage]: https://github.com/
[GitHub Login Page]: https://github.com/login
[About your profile]: https://docs.github.com/en/github/setting-up-and-managing-your-github-profile/about-your-profile
[Setting up a GitHub profile]: #setting-up-a-github-profile
[Git Credential Manager]: https://github.com/GitCredentialManager/git-credential-manager
[Git For Windows]: https://git-scm.com/download/win
[PAT article]: https://github.com/appacademy/practice-for-SETUP-swe-online-setup/blob/main/setup-resources/setting-up-pat.md
[SSH article]: https://hackmd.io/@AgDXdHgSSPKsJIhCxlaTuA/BJtNu88fF
[Select components]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/select-components.png
[VScode default]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/vscode-git-default.png
[Default branch name]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/git-default-branch-name.png
[Git command line]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/git-command-line.png
[Git checkout Unix line endings]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/git-checkout-unix-line-endings.png
[Window default]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/use-window-default.png
[Enable caching]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/enable-caching.png
[Open PowerShell as Admin]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Module-Solo-Prep-Work/setup/open-powershell-as-admin.png
[GCM-browser-screenshot]: https://appacademy-open-assets.s3.us-west-1.amazonaws.com/Modular-Curriculum/content/setup/07-gcm-browser.png
[enable-private-repo-contributions]: https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Modular-Curriculum/content/git/assets/enable-private-repo-contributions.gif
[collaboration-workflow-1]: https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-Solo-Prep-Work/assets/Collaboration-workflow-1.png
[Use GCM in WSL]: #use-gcm-in-wsl
