# Blazor UI Challenge

This project is a Blazor WebAssembly Standalone App built for a UI interaction challenge.

## Challenge Requirements

1. Create a new, standard Blazor Web App project.
2. Add a hamburger button at the top-left corner of the main layout.
3. Implement sidebar behavior:
   - First click on the hamburger button minimizes the sidebar.
   - Second click on the hamburger button expands the sidebar.
   - Hovering over the minimized sidebar also expands it.
4. Push code to a public repository.
5. Make the project live and publicly accessible.

## Implementation in This Project

- Blazor WebAssembly Standalone structure (`Components`, `wwwroot`, `Program.cs`, `wwwroot/index.html`)
- Hamburger button in `Components/Layout/MainLayout.razor`
- Smooth collapsing/expanding sidebar using CSS transitions in `wwwroot/app.css`
- Sidebar state logic:
  - `collapsed` toggled by hamburger click
  - `hovering` enables temporary expansion while minimized

## Routes

- `/` Home
- `/about` About
- `/settings` Settings

## Run Locally

1. Install the .NET 10 SDK.
2. From the project root, run:

```bash
dotnet restore
dotnet run
```

3. Open the URL shown in the terminal.

## Publish

Build production files:

```bash
dotnet publish -c Release
```

Publish output (static site files):

- `bin/Release/net10.0/publish/wwwroot`

## Deploy (Static Hosting)

Any static host works because this is Blazor WebAssembly Standalone.

### GitHub Pages

1. Publish the app:

```bash
dotnet publish -c Release
```

2. Upload/deploy contents of:
   - `bin/Release/net10.0/publish/wwwroot`
3. Enable GitHub Pages in repository settings.
4. Add SPA fallback file for client routes:
   - Copy `index.html` to `404.html` in published output.

### Netlify

1. Publish the app (`dotnet publish -c Release`).
2. Set publish directory to:
   - `bin/Release/net10.0/publish/wwwroot`
3. Add redirect rule so route refreshes work:
   - `/*    /index.html   200`

### Azure Static Web Apps

1. Connect the repository in Azure Static Web Apps.
2. Use app location `/` and output location:
   - `bin/Release/net10.0/publish/wwwroot`
3. Ensure route fallback to `index.html` is enabled.

## Public Repository

- Repository URL: `https://github.com/<your-username>/<your-repo>`

## Live Demo

- Live URL: `https://<your-app-url>`

## Notes

- The sidebar collapses to icon-only navigation.
- Hover on collapsed sidebar expands it while the pointer is over the menu.
- Clicking the hamburger button again restores full expanded state.
- Because this app has client-side routes (`/about`, `/settings`), configure SPA fallback to `index.html` on your host.
