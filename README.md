# Module 4 Assignment: Publish Interactive Reactive App
## cintel-04-local-kristenfinley 
- CONTINUOUS INTELLIGENCE CIS44620 808182FA24
- Kristen Finley


## Objectives

1. **Create a Local Environment**
   - Set up a GitHub repository and clone it locally.
   - Create a virtual environment (`.venv`) in the project directory.
   - Install required packages into the `.venv` environment.

2. **Develop the Shiny App**
   - Open the project in VS Code.
   - Activate the `.venv` environment in the terminal.
   - Build and test the Shiny app (`penguins/app.py`), making edits and rerunning as needed.

3. **Test and Deploy**
   - Use `shinylive` to export the app to a `docs` folder.
   - Host the app on GitHub Pages, with the `docs` folder as the source for deployment.

4. **Make the App Your Own**
   - Customize the browser tab title and, optionally, add a favicon.
   - Document the process in the `README.md` for easy reference.

---

## Setup Process

### Step 1: Repository and Environment Setup
- **Create and Clone Repo**: Create a GitHub repo (`cintel-04-local`) and clone it locally.
- **Virtual Environment Setup**:
  - Open a terminal in the project directory.
  - Create a virtual environment in the `.venv` folder:  
    ```bash
    python -m venv .venv
    ```
  - Activate `.venv`:
    - On Windows:  
      ```bash
      .venv\Scripts\activate
      ```
    - On Mac/Linux:  
      ```bash
      source .venv/bin/activate
      ```
  - Install necessary packages by running:  
    ```bash
    pip install -r requirements.txt
    ```

### Step 2: Develop and Test the App
- **Launch App in VS Code**:
  - Open the project in VS Code, activate the `.venv` environment in the terminal, and run:  
    ```bash
    shiny run --reload --launch-browser penguins/app.py
    ```
  - Edit and rerun as necessary. Remember to activate the `.venv` environment each time.

### Step 3: Build the App for Deployment
- **Export to GitHub Pages**:
  - Clear any static assets:  
    ```bash
    shiny static-assets remove
    ```
  - Export the app to the `docs` folder for GitHub Pages:  
    ```bash
    shinylive export penguins docs
    ```

- **Test Locally**:
  - In the project root, start a local server:  
    ```bash
    py -m http.server --directory docs --bind localhost 8008
    ```
  - Open `http://localhost:8008` in Chrome to view the app. For immediate updates, refresh the browser or open in an incognito tab.

### Step 4: Commit and Push Changes
- **Commit to GitHub**:
  - Run the following commands from a new terminal to add, commit, and push changes:
    ```bash
    git add .
    git commit -m "Your commit message"
    git push -u origin main
    ```

### Step 5: Publish on GitHub Pages
- In your GitHub repo, go to **Settings** > **Pages**.
- Select `main` as the branch and set `docs/` as the publishing source.
- Save and wait for the app to be published. Copy the GitHub Pages URL for sharing.

---

## Additional Customization

- **Change Browser Tab Title**:
  - Open `docs/index.html` and find the `<title>` tag.
  - Replace the inner text with a custom title:
    ```html
    <title>Your Custom App Title</title>
    ```

- **Add a Favicon** (Optional):
  - Generate a favicon at [favicon.io](https://favicon.io) and download the `.ico` file.
  - Save `favicon.ico` in the `docs` folder.
  - Add the following line below the title in `docs/index.html`:
    ```html
    <link rel="icon" type="image/x-icon" href="./favicon.ico">
    ```

---

## Important Commands

- **Activate Virtual Environment**:  
  ```bash
  .venv\Scripts\activate  # Windows
  source .venv/bin/activate  # Mac/Linux

## Technologies Used

This project utilizes several technologies to develop, test, and publish an interactive web app:

1. **Python**: The main programming language used to develop the interactive app.

2. **Shiny for Python**: A framework for creating interactive, client-side web applications with Python. It handles UI rendering and app reactivity without requiring HTML, CSS, or JavaScript.

3. **VS Code**: The Integrated Development Environment (IDE) used to code, manage files, and run the app locally. It also provides terminal access to activate virtual environments and execute commands.

4. **Virtual Environment (`.venv`)**: A project-specific Python environment that isolates package dependencies, ensuring the app’s requirements are met without conflicts.

5. **Git**: Version control software to manage and track code changes locally, as well as push updates to GitHub.

6. **GitHub**: An online repository for storing code, collaborating, and hosting the project. It also enables free hosting of the client-side app through GitHub Pages.

7. **GitHub Pages**: A GitHub feature that hosts the static version of the app in the `docs` folder, making it accessible via a `github.io` URL.

8. **Shinylive**: A tool that converts Shiny Python apps into static assets, allowing the app to be hosted on GitHub Pages without requiring a backend server.

9. **HTTP Server (Python)**: Used for local testing of the static app build. The command `python -m http.server` allows previewing the app locally before deployment.

10. **Browser (Chrome recommended)**: For testing and running the interactive app both locally and once it’s published on GitHub Pages.

### Optional (for additional customization):

11. **Favicon.io**: A tool for creating a custom favicon, adding a unique touch to the web app’s branding.

Each technology listed above plays a vital role in creating a streamlined workflow for Python-based web development, from initial setup to final deployment.



### Screenshot
![TBD](TBD.png)

## Acknowledgments
- Special thanks to the developers of Shiny, Matplotlib, and Seaborn for their powerful data visualization libraries.
- Thanks to ChatGPT for assistance in code development and debugging.
