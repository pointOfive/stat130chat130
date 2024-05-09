# Git instruction

Git is an exceptionally powerful version control tool that we'll be utilizing for our project. Its robust capabilities will help us manage our project's codebase efficiently.

For those who are new to Git, I’ve outlined some basic instructions below. These should be more than sufficient for our project needs. 

## Before your creation

### Install git on your computer

To ensure a smooth workflow for our project, please install Git on your computer. We will use the Terminal for most of our interactions with Git, which allows for direct command-line access to all Git features. 

Here’s how to install Git:

1. **Open your Terminal.**
2. **Install Git using Homebrew** (for macOS users):
    - If you do not have Homebrew installed, you can install it by pasting the following command into your Terminal and pressing Enter:
    
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
    
    - Once Homebrew is installed, you can install Git by running:
    
    ```bash
    brew install git
    ```
    
3. **For Windows users**:
    - Download the Git installer from [Git’s official site](https://git-scm.com/).
    - Run the installer and follow the instructions.
4. **Verify the installation**:
    - To check if Git is installed correctly, type the following command in your Terminal or Command Prompt:
    
    ```css
    git --version
    ```
    
    - This command should return the installed version of Git.

By following these steps, you will have Git installed and ready to manage our project's files and revisions.

### Clone the project into your device and create a new branch

To start collaborating on our project, you'll first need to clone the repository from GitHub to your local machine and then create a branch for your contributions. Here’s how to do it step-by-step:

1. **Cloning the Repository**
    - **Find the Repository URL**: Go to the GitHub page of the project. Click on the green ‘Code’ button, and copy the URL under 'HTTPS'. It should look something like this:
        
        ‘**`https://github.com/path/to/repository.git`**’
        
    - **Clone the Repository**: Open your Terminal or Command Prompt and run the following command:

```bash
git clone <paste-the-copied-URL-here>
```

Replace **`<paste-the-copied-URL-here>`** with the URL you copied from GitHub.

2. Creating a New Branch
- **Navigate into the Repository Directory**:

```
cd <repository-name>
```

Replace **`<repository-name>`** with the name of the folder that was created when you cloned the repository.

**Create and Switch to Your New Branch**:

```
git checkout -b <branch-name>
```

Replace **`<branch-name>`** with a descriptive name for your new branch, for example, **`feature_xyz`**. This command creates a new branch and switches you to it immediately.

Now, you have a local copy of the project and are all set to start making changes on your new branch! 

### **After You Have Done Your Work**

After making changes to your files, follow these steps to commit your changes and prepare for a pull request:

1. **Add Changes to Staging:**

```
git add <file-name>
```

Replace **`<file-name>`** with the name of the file you changed, or use **`.`** to add all changed files.

2. **Commit Your Changes:**

```
git commit -m "<Your commit message>"
```

Replace **`<Your commit message>`** with a brief description of what has been changed.

3. **Push to Remote Repository:**

```bash
git push origin <branch-name>
```

4. **Update Your Branch with Latest Main Branch Changes:**

```bash
git checkout main
git pull origin main
git checkout <branch-name>
git rebase main
# If there are conflicts, resolve them, and then continue the rebase. If forced update is needed:
git push -f origin <branch-name>
```

5. **Create a Pull Request:**
    - Go to GitHub and navigate to the repository page. You should see your branch and have the option to "Create a pull request.”
    - Follow the instructions on GitHub to create the pull request.
6. **After Pull Request Approval:**
    - Once your pull request is approved and merged, you can delete your branch on GitHub.
    - Clean up your local repository:
    
    ```
    git checkout main
    git pull origin main
    git branch -D <branch-name>
    ```
    
    Now, you are all set to start a new task by creating a new branch if needed!
