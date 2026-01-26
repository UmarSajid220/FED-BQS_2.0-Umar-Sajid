# **Development Environment and Git**

### **Introduction**

Welcome to the start of your coding journey\! This guide is a one-stop resource designed to walk you through the essential first steps every new developer must take: setting up a professional development environment and mastering the basics of Git and GitHub. While some of these steps might seem complex at first, they represent the foundational skills used by modern developers every single day. Our goal is to make this process clear and manageable, providing you with the solid footing you need to build amazing things.

\--------------------------------------------------------------------------------

## **1\. Setting the Stage: Your Professional Development Environment**

### **1.1. Why a Proper Environment Matters**

Many online courses use in-browser "sandboxes" to get you coding quickly. While convenient, they don't reflect how software is built in the real world. The most important step you can take for long-term success is to set up and operate in a real development environment on your own computer. Installing packages, configuring tools, and even learning a new operating system can be challenging, but it is an invaluable, real-world skill you will carry with you for the rest of your career.

### **1.2. Analyzing Your Operating System (OS) Options**

The tools used in modern web development are built with a Unix-based system in mind. Here is an evaluation of the operating systems recommended for this curriculum.

* **Supported Systems:**  
  1. **macOS:** If you're using a Mac, you're in great shape. macOS is a Unix-based system that is well-suited for development and requires minimal setup to get started.  
  2. **Linux (Ubuntu):** For non-Mac users, Linux is the recommended choice. It is a free, open-source operating system where most development tools run natively. On Linux, tools are often updated more often, have more information available for troubleshooting, and just plain run better. This guide specifically uses Ubuntu or its lighter-weight alternative, Xubuntu.  
* **Options for Windows Users:** Native Windows **is not supported** by this curriculum. Because development tools are designed for a Linux environment, Windows users must create one using one of the following three methods.  
  1. **Virtual Machine (Recommended for Beginners):** A virtual machine (VM) is an emulation of a computer that runs as an application within your existing Windows OS. This is the easiest, most reliable, and completely risk-free option. It allows you to run a full Linux environment without altering your computer's main setup, and it can be easily removed if needed.  
  2. **Dual-Booting:** This method involves installing two separate operating systems on one computer, allowing you to choose between Windows or Linux when you start your machine. The primary advantage is performance, as Linux gets full access to your computer's resources. However, it involves partitioning your hard drive, which carries some risk if not done carefully.  
  3. **Windows Subsystem for Linux (WSL2 \- Advanced):** WSL2 is a powerful tool from Microsoft that allows you to run a full Linux environment directly within Windows. While this option avoids the need for a VM or dual-booting, it can cause confusion for new learners because you will be working across two different operating systems simultaneously.  
* **Chromebooks:** For those using a Chromebook, enabling the built-in Linux Development Environment is another viable option for creating a suitable setup.

### **1.3. Choosing Your Web Browser: Google Chrome**

For this curriculum, **Google Chrome is the required browser**. This choice is intentional. Chrome holds an overwhelming usage share among both developers and consumers, and more importantly, it includes powerful, built-in developer tools that you will use constantly to inspect, debug, and test your applications.

Now that your environment is staged, it's time to understand the critical tools you'll be using within it, starting with Git.

\--------------------------------------------------------------------------------

## **2\. Understanding Version Control: What Are Git and GitHub?**

### **2.1. The Power of Version Control**

At its core, Git is like an **epic save button** for your projects. Officially, Git is known as a version control system. It allows you to track changes to your files, maintain a complete history of every version, and collaborate effectively with others.

### **2.2. Git vs. a Standard Text Editor**

The "save" function in Git is fundamentally different from a standard text editor's save.

| Text Editor Save | Git Commit |
| ----- | ----- |
| Records all content as a single file, **overwriting the previous state**. | Records the ***differences*** in files and folders. |
| To keep a history, you must manually create duplicate files (e.g., essay-draft1.doc, essay-final.doc). | Maintains a **complete historical record** of every save automatically. |

### **2.3. Git vs. GitHub: Local vs. Remote**

It's crucial to understand that Git and GitHub are not the same product.

* **Git:** This is the version control software that you install and run on your ***local*** machine. It tracks your files and manages your project's history.  
* **GitHub:** This is a ***remote*** storage service on the web that hosts your Git projects. It acts as a central hub for your code, allowing you to create a portfolio, share your work, and collaborate with other developers.

### **2.4. Why These Tools are Essential**

Proficiency with Git and GitHub is a non-negotiable skill for modern developers. Here’s why:

* **For Individuals:** It allows you to review your project's history and growth over time. If you make a mistake, you can easily restore a previous version of a file.  
* **For Collaboration:** It enables you to share your projects with others, work on the same code simultaneously, and manage contributions in a clean, organized way.  
* **For Your Career:** Almost all software companies consider Git proficiency an essential skill. A well-maintained GitHub profile acts as a portfolio of your work, providing tangible proof of your capabilities to potential employers.

With a conceptual understanding in place, let's move on to the practical steps of installing and configuring these essential tools.

\--------------------------------------------------------------------------------

## **3\. Installation and Configuration: Getting Your Tools Ready**

### **3.1. Preparing for Installation**

This section provides a step-by-step guide to installing Git, creating a GitHub account, and securely linking the two. By following these steps carefully, you will ensure a smooth and professional setup, ready for your first project.

### **3.2. Step 1: Installing Git**

* **For Linux Users:**  
  1. First, update your system's package list and upgrade existing packages:  
  2. You likely have Git installed already, but to make sure you have the most up-to-date version, run the following commands.  
     1. Add the official Git Personal Package Archive (PPA) to your system's sources:  
     2. Update your package list again to include the packages from the new PPA:  
     3. Install the latest version of Git:  
* **For macOS Users:**  
  1. Git is installed using Homebrew, a package manager for macOS. If you don't have it, install it with this command:  
  2. With Homebrew installed, update or install Git with a simple command:  
* **For ChromeOS Users:**  
  1. First, update your system's package list and upgrade existing packages:  
  2. Next, install Git using the standard package manager:  
  3. After installation, verify your Git version (see below). If it is less than 2.28, you will need to add the official Git PPA to get a more recent version by running these commands:  
* **Version Verification (All Systems):**  
  1. It is critical to verify that your installation was successful and that you are using a modern version of Git.  
  2. Run the following command. The version number returned must be **at least 2.28**.

### **3.3. Step 2: Setting Up GitHub and Git Configuration**

1. **Create a GitHub Account:** Go to [GitHub.com](https://github.com/) and create a free account. During setup or in your account's Email Settings, you can select "Keep my email addresses private." This prevents your personal email from being exposed in your public commits. If you choose this option, make a note of the private @users.noreply.github.com email address provided, as you will need it shortly.  
2. **(Optional) Enable Two-Factor Authentication (2FA):** 2FA adds an extra layer of security to your account by requiring a second form of verification when you log in. This is highly recommended.  
3. **Configure Git Locally:** You need to tell Git who you are. These details will be attached to every commit you make. Run the following commands, replacing the placeholder text with your information.  
4. **For macOS Users Only: Ignore .DS\_Store files:** macOS creates hidden .DS\_Store files that hold folder metadata. To prevent these from cluttering your commits, run these two commands to tell Git to ignore them globally.  
5. **Verify Configuration:** Check that your information was saved correctly.

### **3.4. Step 3: Connecting to GitHub with SSH**

An SSH key is a secure identifier that acts like a long, unique password. It allows your computer to communicate securely with GitHub without you needing to enter your username and password every time you push your code.

1. **Check for an Existing Key:** First, check if you already have a key.  
2. If the command returns "No such file or directory," you need to create a new key. Otherwise, you can skip to the next step.  
3. **Generate a New SSH Key:** Use the following command to create a new, secure SSH key.  
4. When prompted for a file location (e.g., \~/.ssh/id\_ed25519), press Enter to accept the default. You will then be prompted to create an optional password for your key. This adds another layer of security but is not required.  
5. **Add the SSH Key to GitHub:**  
   * Copy your *public* key to your clipboard. The cat command displays the file's content in the terminal.  
   * Navigate to GitHub in your browser. Go to your **Profile Picture \> Settings \> SSH and GPG keys**.  
   * Click **New SSH Key**.  
   * Give the key a descriptive **Title** (e.g., "My Ubuntu Laptop") and paste the copied key into the **Key** field. Click **Add SSH key**.  
6. **Test the Connection:** Follow GitHub's official directions for testing your SSH connection. A successful test will return the following message:

With your tools installed and configured, you are now ready for the exciting part: using Git to manage your first project.

\--------------------------------------------------------------------------------

## **4\. The Core Git Workflow: A Practical Walkthrough**

### **4.1. Your First Project**

This section will guide you through the **basic Git workflow**. These are the commands you will use 70-80% of the time as a developer. We will create a project locally, track its changes with Git, and synchronize it with a remote repository on GitHub.

### **4.2. Step 1: Create and Clone Your Repository**

1. **On GitHub:** Create a new repository. Give your repository the name git\_test. Switch on the "Add README" option (this automatically creates a README.md file in your new repository).  
2. **Copy the SSH URL:** On your new repository's page, click the green **"Code"** button. Select the **SSH** option and copy the URL. It should look like git@github.com:USER-NAME/git\_test.git.  
3. **On Your Local Machine:** Open your terminal. It's good practice to keep all your projects in one place. Create and navigate into a repos directory in your home folder.  
4. **Clone the Repository:** Use the git clone command followed by the SSH URL you copied. This downloads a complete copy of the remote repository to your local machine.  
5. **Verify the Connection:** Move into your new project directory and check your remote connections.  
6. The output shows the URL of your remote repository. By default, Git gives this remote connection the name origin.

### **4.3. Step 2: The Two-Stage System: Add and Commit**

1. **Create a New File:** Let's create a simple text file in your project directory.  
2. **Check the Status:** The git status command is your best friend. It tells you the current state of your project.  
3. The new file appears in red under "Untracked files." This means Git sees the file but is not yet tracking changes to it.  
4. **Stage the File:** To tell Git you want to include this file in your next save, you must add it to the "staging area." Think of this as a waiting room for your changes.  
5. **Check the Status Again:** Run git status once more. The file is now green and listed under "Changes to be committed."  
6. **Commit the Change:** A "commit" takes a permanent snapshot of all the files in the staging area. The \-m flag allows you to add a descriptive message explaining the change.

### **4.4. Step 3: Modifying Files and Making More Commits**

1. **Modify a File:** Open the README.md file in a text editor and add the text "Hello Odin\!".  
2. **Check Status:** Run git status. You'll see README.md is now listed under "Changes not staged for commit."  
3. **Stage and Commit Multiple Files:** Now, open hello\_world.txt and add some text to it. To stage all modified and new files in the current directory, you can use git add . (the period represents the current directory).

### **4.5. Step 4: Pushing to GitHub**

1. **Push Your Commits:** Your commits currently exist only on your local machine. To upload them to GitHub, use the git push command. This command sends your committed snapshots from your local main branch to the remote repository named origin.  
2. Since you are not dealing with another branch (other than main) or a different remote, you can often use git push as a shorter alternative.  
3. **Verify on GitHub:** Refresh your repository page on GitHub. You should now see your new files and the changes you just made.

### **4.6. Step 5: Viewing Your History**

To see a complete history of every commit you have made, use the git log command. This will show the author, date, and commit message for each snapshot. You can press q to exit the log view.

git log

This workflow forms the backbone of your daily work with Git. Now, let's summarize these commands and discuss some best practices.

\--------------------------------------------------------------------------------

## **5\. Quick Reference and Best Practices**

### **5.1. Building Good Habits**

Knowing the commands is only half the battle; using them effectively is what makes you a great developer and collaborator. Adopting best practices like writing clear commit messages and making "atomic" commits will make your project history clean, understandable, and easy to manage.

### **5.2. Git Command Cheatsheet**

| Command | Purpose |
| ----- | ----- |
| git clone \[url\] | Copies a remote repository onto your local machine. |
| git status | Shows the current status of your working directory and staging area. |
| git add \[file\] or git add . | Adds one or all files to the staging area. |
| git commit \-m "\[message\]" | Records a snapshot of the staged files with a descriptive message. |
| git log | Displays the history of commits for the current branch. |
| git push origin main | Uploads local commits to the remote repository on GitHub. |

### **5.3. Understanding Atomic Commits**

An **atomic commit** is a best practice where each commit includes changes related to only one specific feature or task. This approach has two key benefits:

1. If a change introduces a bug, it is easy to revert that single, specific commit without affecting other unrelated work.  
2. It forces you to write clearer, more focused commit messages that accurately describe the single task accomplished in that commit.

### **5.4. A Note on Editing Files**

For now, you should avoid editing files directly on the GitHub website. While it may seem tempting for quick fixes, doing so can create synchronization issues that require more advanced Git knowledge to resolve. As a best practice, always make your changes on your local machine, then commit and push them to GitHub.

### **5.5. Making Commits Easier**

Sometimes you might forget to add the \-m flag when you type git commit. By default, this will open a command-line text editor like Vim, which can be confusing for beginners. You can configure Git to use VS Code as your default commit editor instead.

git config \--global core.editor "code \--wait"

Now, if you run git commit, a new tab will open in VS Code where you can type your commit message, save it, and close the tab to finalize the commit.

You have now covered the essentials of setting up your environment and using Git. The final sections will help you solidify your knowledge and point you toward further learning.

\--------------------------------------------------------------------------------

## **6\. Knowledge Check**

### **6.1. Test Your Understanding**

Use the following questions to reflect on what you've learned. You are not expected to have memorized everything, but you should be able to reason through the answers.

* What operating systems and browser does The Odin Project support?  
* What kind of program is Git?  
* What are the differences between Git and a text editor in terms of what they save?  
* Does Git work locally or remotely? Does GitHub work locally or remotely?  
* Why are Git and GitHub useful for both individual developers and teams?  
* How do you create a new repository on GitHub?  
* How do you copy a repository from GitHub onto your local machine?  
* What is the default name of your remote connection (e.g., origin)?  
* Explain what origin is in git push origin main.  
* Explain what main is in git push origin main.  
* Explain the two-stage system that Git uses to save files (working directory and staging area).  
* How do you check the status of your current repository?  
* How do you add files to the staging area?  
* How do you commit staged files with a message?  
* How do you push your changes to your repository on GitHub?  
* How do you view the history of your previous commits?

\--------------------------------------------------------------------------------

## **7\. Additional Resources**

### **7.1. Continue Your Learning**

* [**GitHub Docs: Configuring two-factor authentication**](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)**:** The official guide for setting up 2FA to secure your GitHub account.  
* [**GitHub Docs: Testing your SSH connection**](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)**:** The official guide to ensure your SSH key is set up correctly and your machine can communicate with GitHub.  
* [**Pro Git Book (Chapters 1.1-1.4)**](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)**:** Recommended reading to learn the differences between local, centralized, and distributed version control systems.  
* [**Google's guide to turn on Linux on ChromeOS**](https://support.google.com/chromebook/answer/9145439)**:** Instructions for Chromebook users to enable the required Linux Development Environment.