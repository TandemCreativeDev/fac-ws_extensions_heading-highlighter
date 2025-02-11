# FAC Browser Extension Workshop: Heading Highlighter

## The Problem

We need to make an accessibility tool that can visually audit our webpage's coded heading hierarchy. For this, we want a browser extension that can access the page that we are on, find all html heading elements and highlight them in a colour that will stand out.

We are not concerned about this working accross tabs and page reloads.

> [!TIP]
> We will need a content script to interact with the page's DOM elements. Because we are not concerned with preserving our highlight state accross tabs and page reloads, we do not need a background script and can run everything through [chrome's scripting service](https://developer.chrome.com/docs/extensions/reference/api/scripting) and [window messaging](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage).

## Getting Set Up

### **1. Initiate Plasmo Tailwind Project**

1a. In your work directory, run this command to initiate and a new plasmo project with tailwind:

```sh
pnpm create plasmo --with-tailwindcss
```

1b. Alternatively, if you wish to use vanilla css styling, simply initiate a new plasmo project:

```sh
pnpm create plasmo
```

2. Name the project `heading-highlighter-1` and run through the other setup configuration options.

3. Go into the project folder:

```sh
cd heading-highlighter-1
```

4. Open in your favourite code editor (if configured):

```sh
code .
```

### **2. Project Folder Set Up**

1. If you want a recommended folder structure, see section `Recommended Folder Structure`, otherwise design your own structure and delete all non-applicable files inside `src` generated by plasmo's default app.

2. Create files and folders for your solution inside `src`.

### **3. Get Coding!** 🚀

## Useful Resources

- [Plasmo Docs](https://docs.plasmo.com/)
- [Plasmo Example Repo](https://github.com/PlasmoHQ/examples)
- [Chrome Extension Docs](https://developer.chrome.com/docs/extensions)

## Recommended Folder Structure

The folder structure used for this exercise is as follows:

```bash
src/
├── features/
│   └── toggle.tsx
├── utils/
│   └── getCurrentTabId.ts
├── content.ts
├── popup.tsx
└── style.tsx
```

> [!NOTE]
> This is not the only way to solve this problem, but for plasmo to work you will need as a minimum `popup.tsx` in the `src` folder and either `content.ts` in the `src` folder or a `contents` folder with code files that interact with the webpages' DOM elements.

## Run Solution

If you want to run this solution to see what it should look like, follow these steps:

### **1. Clone Repo**

In your work directory, run this command to clone the repo and go into the local repo folder:

```sh
git clone https://github.com/TandemCreativeDev/fac-ws_extensions_heading-highlighter.git
cd fac-ws_extensions_heading-highlighter
```

### **2. Change Branch**

Checkout the branch for this exercise by running:

```sh
git checkout exercise1
```

### **3. Install Dependencies**

Ensure you have **Node.js** and **pnpm** installed. Then, install Plasmo dependencies:

```sh
pnpm install
```

The following step can be used in your project aswell to test changes you make in the code dynamically:

### **4. Run in Development Mode**

You can run the extension in **development mode** to test it live:

```sh
pnpm dev
```

Then, open Chrome and go to:

```
chrome://extensions/
```

- Enable **Developer Mode** (toggle in the top-right corner).
- Click **Load Unpacked** and select the `chrome-mv3-dev` in your project's `build` folder.

---

## Building & Installing for Production

To create a production-ready version of the extension:

```sh
pnpm build
```

This will generate a `build` folder. To install it in Chrome:

1. Open `chrome://extensions/`
2. Enable **Developer Mode**.
3. Click **Load Unpacked**.
4. Select the `chrome-mv3-prod` in your project's `build` folder.

> [!WARNING]
> FOR LINUX USERS\
> When running `pnpm dev` or `pnpm build` in a Linux environment you may come accross dumping errors or errors related to a package called `sharp`. You may see an error such as:
>
> ```sh
>  ELIFECYCLE  Command failed with exit code 139.
> ```
>
> These seem to be caused by the latest `plasmo` dependencies under its tailwind configuration. Although such an error may pop up, the project has built and you can load it into Chrome as described above.

---
