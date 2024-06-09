<body>
    <h1>Deploy React Web Application on Netlify</h1>
    <h2>Introduction</h2>
    <p>This guide will help you deploy your React web application on Netlify and fix any navigation errors using a <code>netlify.toml</code> file.</p>
    
    <h2>Steps to Deploy</h2>
    
    <h3>1. Create a React Application</h3>
    <pre><code>npx create-react-app my-app</code></pre>
    <p>Navigate into your project directory:</p>
    <pre><code>cd my-app</code></pre>
    
    <h3>2. Initialize a Git Repository</h3>
    <pre><code>git init
git add .
git commit -m "Initial commit"</code></pre>
    
    <h3>3. Push to GitHub</h3>
    <p>Create a repository on GitHub and push your project:</p>
    <pre><code>git remote add origin https://github.com/your-username/your-repo-name.git
git branch -M main
git push -u origin main</code></pre>
    
    <h3>4. Deploy on Netlify</h3>
    <p>Login to Netlify and create a new site from Git:</p>
    <ul>
        <li>Choose your GitHub repository</li>
        <li>Set the build command to <code>npm run build</code></li>
        <li>Set the publish directory to <code>build</code></li>
    </ul>
    
    <h3>5. Fix Navigation Errors</h3>
    <p>To fix navigation errors (e.g., 404 errors on page refresh), create a <code>netlify.toml</code> file in the root of your project with the following content:</p>
    <pre><code>[build]
  command = "npm run build"
  publish = "build"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200</code></pre>
    
    <h3>6. Commit and Push the <code>netlify.toml</code> File</h3>
    <pre><code>git add netlify.toml
git commit -m "Add netlify.toml to fix navigation errors"
git push</code></pre>
    
    <h3>7. Redeploy the Site</h3>
    <p>Go to your Netlify dashboard and trigger a redeploy of your site to apply the changes.</p>
    
    <h2>Conclusion</h2>
    <p>By following these steps, you should have your React web application deployed on Netlify without navigation errors. The <code>netlify.toml</code> file ensures that all navigation requests are correctly redirected to your <code>index.html</code> file.</p>
</body>
