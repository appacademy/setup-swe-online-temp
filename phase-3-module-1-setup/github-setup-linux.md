# Git and GitHub Setup for Linux

GitHub is one of the key collaborative tools that enable teams of developers to
build and maintain web applications using the Git version control system. In
this article, you'll learn more about some of the key features of the Git and
GitHub, as well as set up an account if you do not have one already.

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

## Installing Git

Here is a starting point for you to install [Git] on your own.

> _Note: You may need to do some trouble-shooting to get your setup to work.
> Keep in mind that Linux is not officially supported at App Academy. If you
> struggle with your Linux setup, you are strongly encouraged to switch to a Mac
> or Windows environment so you can benefit from Instructor support with your
> environment setup._

## Installing GCM

Because GitHub allows you to share code with other developers, there needs to be
a way to authenticate to make sure that you are authorized to access or
contribute new code.

Thankfully, git handles this authentication flow automatically. But for GitHub,
there are several options for handling this authentication. These instructions
will walk you through setting up authentication through Git Credential Manager,
which is App Academy's preferred method.

Here is a starting point for you to install [Git Credential Manager].

[Git Credential Manager]: https://github.com/git-ecosystem/git-credential-manager

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
[Git]: https://git-scm.com/
[enable-private-repo-contributions]: https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Modular-Curriculum/content/git/assets/enable-private-repo-contributions.gif
[collaboration-workflow-1]: https://appacademy-open-assets.s3-us-west-1.amazonaws.com/Module-Solo-Prep-Work/assets/Collaboration-workflow-1.png
