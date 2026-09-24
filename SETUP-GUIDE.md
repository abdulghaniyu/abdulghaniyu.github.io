# Setup guide: your academic website on GitHub Pages

You don't need to install anything. You'll do everything in your web browser on github.com.
Plan for about 30 minutes the first time.

---

## Part 1. Put the site online

### Step 1. Create a GitHub account
1. Go to https://github.com/signup.
2. Pick a short, professional username. Your site address will be `https://USERNAME.github.io`, so choose something like `agalidu` or `alidu-ag`.
3. Verify your email address.

### Step 2. Create the repository
1. Click the **+** in the top right, then **New repository**.
2. In **Repository name**, type exactly `USERNAME.github.io`, using your own username. The name must match exactly or the site won't publish.
3. Set it to **Public**.
4. Leave "Add a README" unticked.
5. Click **Create repository**.

### Step 3. Upload the site files
1. Unzip `academic-site.zip` on your computer.
2. Open the unzipped folder. You should see `_config.yml`, `index.html`, and folders like `_data`, `_includes` and `assets`.
3. On your new repository page, click **uploading an existing file**.
4. Select everything **inside** the folder and drag it into the browser window. Don't drag the outer folder itself.
5. Check that the upload list includes the folders starting with `_`.
6. Scroll down and click **Commit changes**.

### Step 4. Turn on GitHub Pages
1. In your repository, click **Settings**, then **Pages** in the left menu.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Set **Branch** to `main` and the folder to `/ (root)`, then click **Save**.

### Step 5. Check it's live
1. Click the **Actions** tab. You'll see a job called "pages build and deployment".
2. Wait for a green tick. This takes 1 to 3 minutes.
3. Open `https://USERNAME.github.io`.

---

## Part 2. Personalise it

Edit any file on GitHub by opening it and clicking the pencil icon. Click **Commit changes** to save. The site rebuilds itself in 1 to 2 minutes.

Tip: press the `.` key on your repository page to open a full editor (github.dev) in your browser. It's easier for editing several files at once.

### Step 6. Set your site address
Open `_config.yml` and change this line:
```
url: "https://YOUR-GITHUB-USERNAME.github.io"
```

### Step 7. Add your photo
1. Use a square photo, at least 400 × 400 pixels and under 500 KB.
2. Name it `profile.jpg`.
3. Go to the `assets/img` folder, click **Add file**, then **Upload files**, and upload it.
4. Open `_data/profile.yml` and change the photo line to:
```
photo: /assets/img/profile.jpg
```

### Step 8. Add your CV
1. Export a short academic CV (2–3 pages) as a PDF named `cv.pdf`.
2. Upload it to the `assets/files` folder.
The **Download CV** button and the **CV** menu link will then work.

### Step 9. Fill in your links
Open `_data/profile.yml`. Any link with `url: ""` stays hidden. Fill in the ones you want to show:
- **Google Scholar:** create a profile at https://scholar.google.com/citations, then paste your profile link.
- **GitHub:** `https://github.com/USERNAME`
- **OSF:** your OSF profile link.
- **BaoHope Foundation:** the foundation's website or social page.

### Step 10. Edit your About text
Open `index.html` and change the text between the `<p>` and `</p>` tags. Leave the lines with `{% ... %}` alone.

---

## Part 3. Keep it up to date

All your content lives in plain-text files in the `_data` folder.

Rules for these `.yml` files:
- Use spaces, never tabs. Indentation must line up exactly with the example above it.
- Put text in double quotes if it contains a colon (`:`).
- New entries go at the top of the list.

### Add a news item (right sidebar)
Open `_data/news.yml` and add this at the top:
```
- date: "Dec 2026"
  text: Your news here. Links look like [this](https://example.com).
```
The sidebar shows the six newest items.

### Add a publication
Open `_data/publications.yml`, copy an existing block, and edit it. Put `**` around your own name to make it bold. `section` must be one of `Journal articles`, `Under review`, or `Protocols and other works`.

When a paper under review is accepted, change its `section` to `Journal articles`, add a `year`, and add a DOI link.

### Add a talk or poster
Open `_data/talks.yml` and copy an existing block. Add `upcoming: true` for future events, and remove it once the event has passed.

### Add a project
Open `_data/projects.yml` and copy a block. Set `featured: true` to show it on the home page. Keep 2 or 4 projects featured so the grid stays even.

### Write a blog post
1. Go to the `_posts` folder and click **Add file**, then **Create new file**.
2. Name it with this pattern: `YYYY-MM-DD-short-title.md`, for example `2026-10-15-what-is-digital-health-equity.md`.
3. Start the file with this header, then write your post below it in Markdown:
```
---
layout: post
title: "What is digital health equity?"
tags: [Digital health equity, Concepts]
---

Your first paragraph goes here.

## A subheading

- A bullet point
- **Bold text** and *italic text*
- [A link](https://example.com)

![Describe the image](/assets/img/my-figure.png)
```
4. Commit. The post appears on the Blog page, in the right sidebar and in the RSS feed.

Upload images for posts to `assets/img` first.

---

## Part 4. Troubleshooting

**The site didn't update.** Open the **Actions** tab. A red cross means the build failed. Click it to read the error. It usually names the file and line.

**Most common causes of a failed build:**
- A tab instead of spaces in a `.yml` file.
- A colon inside unquoted text in a `.yml` file.
- A blog post file name without the `YYYY-MM-DD-` date at the start.
- A blog post dated in the future. Jekyll hides future-dated posts until that date.

**The changes are live but I can't see them.** Hard-refresh your browser: Ctrl + Shift + R on Windows, Cmd + Shift + R on Mac.

**To undo a mistake:** open the file, click **History**, pick the last version that worked, and copy its content back.

---

## Part 5. After launch

1. Add your site to your ORCID record under **Websites & social links**.
2. Add it to your LinkedIn profile, Google Scholar homepage field, and email signature.
3. Optional: buy your own domain (for example `abdulalidu.com`, about $12 a year) and connect it under **Settings**, then **Pages**, then **Custom domain**.
4. Optional: submit your site to Google Search Console (https://search.google.com/search-console) so it appears in search results faster. The site already publishes a `sitemap.xml` for this.

A note on branding: the site uses University of Michigan colours, but not the Block M or other university logos. U-M's brand guidelines reserve those for official units, so leave them off a personal site.
