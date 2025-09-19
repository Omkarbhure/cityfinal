# Deploying to Vercel

This guide will walk you through deploying your Vite application to Vercel.

## 1. Connect Your Repository to Vercel

1.  Go to the [Vercel dashboard](https://vercel.com/dashboard) and click "Add New...".
2.  Select "Project" and then choose the Git repository that contains your project.
3.  Vercel will automatically detect that you have a Vite application and configure the build settings for you.

## 2. Configure Build Settings

If Vercel does not automatically detect the settings, or if you need to configure them manually, use the following:

*   **Framework Preset:** `Vite`
*   **Build Command:** `npm run build`
*   **Output Directory:** `dist`
*   **Install Command:** `npm install`

## 3. Deploy

Click the "Deploy" button. Vercel will start the build process and deploy your application. Once the deployment is complete, you will be given a URL to your live site.

## Deploying the Backend

This project includes a `server.js` file that runs an Express server. To deploy both the frontend and the backend to Vercel, you need to configure Vercel to handle the server as a [Vercel Function](https://vercel.com/docs/functions/serverless-functions).

A `vercel.json` file has been created for you with the necessary configuration. This file tells Vercel to:
1.  Deploy the `server.js` file as a Node.js serverless function.
2.  Build the frontend application and serve it from the `dist` directory.
3.  Rewrite all requests to `/api/...` to the serverless function.

When you deploy to Vercel with the `vercel.json` file in your repository, Vercel will automatically use this configuration to deploy both the frontend and the backend.
