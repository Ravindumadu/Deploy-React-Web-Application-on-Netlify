Deploy React Web Application on Netlify
=======================================

Introduction
------------

This guide will help you deploy your React web application on Netlify and fix any navigation errors using a `netlify.toml` file.

Steps to Deploy
---------------

### 1\. Create a React Application

    npx create-react-app my-app

Navigate into your project directory:

    cd my-app

### 2\. Initialize a Git Repository

    git init
    git add .
    git commit -m "Initial commit"

### 3\. Push to GitHub

Create a repository on GitHub and push your project:

    git remote add origin https://github.com/your-username/your-repo-name.git
    git branch -M main
    git push -u origin main

### 4\. Deploy on Netlify

Login to Netlify and create a new site from Git:

*   Choose your GitHub repository
*   Set the build command to `npm run build`
*   Set the publish directory to `build`

### 5\. Fix Navigation Errors

To fix navigation errors (e.g., 404 errors on page refresh), create a `netlify.toml` file in the root of your project with the following content:

    [build]
      command = "npm run build"
      publish = "build"
    
    [[redirects]]
      from = "/*"
      to = "/index.html"
      status = 200

### 6\. Commit and Push the `netlify.toml` File

    git add netlify.toml
    git commit -m "Add netlify.toml to fix navigation errors"
    git push

### 7\. Redeploy the Site

Go to your Netlify dashboard and trigger a redeploy of your site to apply the changes.

Conclusion
----------

By following these steps, you should have your React web application deployed on Netlify without navigation errors. The `netlify.toml` file ensures that all navigation requests are correctly redirected to your `index.html` file.
