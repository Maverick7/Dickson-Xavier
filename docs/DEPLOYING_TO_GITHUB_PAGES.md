# Publishing the graph resume to GitHub Pages

The `docs/index.html` file is already a static, GitHub Pages–compatible entry point. Use the steps below to ensure it replaces any older site and to understand your domain options.

## Point Pages at the `docs/` folder
1. Push the latest commit to your GitHub repository.
2. In GitHub, open **Settings → Pages** for the repository.
3. Under **Source**, choose the **main (or default) branch** and set the **/docs** folder.
4. Click **Save**. GitHub will publish to `https://<username>.github.io/<repo>/` and usually refreshes within a couple of minutes.
5. If you still see the old site, force-refresh the browser (Shift+Reload) or wait for the CDN cache to expire (can take ~5–10 minutes). You can also open the site in a private window to bypass cache.

## Why `maverick7.github.io` still shows the old site
User/organization sites live at `https://<username>.github.io/` and are bound to the account name. If your previous user site was published from another repository or branch, GitHub will keep serving that content until you update its source or disable Pages there. Project sites (like this resume) live under `https://<username>.github.io/<repo>/` and won’t overwrite your user site unless you configure that exact repo as the user site.

## Changing the domain name
- **To use `dickson.xavier.github.io`:** this is not possible while the account name is `maverick7`, because GitHub reserves the `*.github.io` domain to match the exact username or organization name. To get that hostname you would need to rename the GitHub account to `dickson.xavier` (not allowed because of the dot) or create a new account/organization whose name matches the desired subdomain.
- **Custom domain option:** you can point any domain you own (e.g., `dicksonxavier.com` or `resume.dicksonxavier.com`) to the Pages site instead. In **Settings → Pages**, set your custom domain and create a DNS CNAME record pointing to `<username>.github.io`. GitHub will issue TLS automatically.
- **Project URL:** even without a custom domain, the resume will be available at `https://maverick7.github.io/<repo>/` once the Pages source is set to the `/docs` folder.

## Verifying the latest build
After saving the Pages settings, use the **Visit site** link in the Pages panel. Make sure the page shows the updated graph resume and that the footer in your browser indicates the load occurred moments ago (or check DevTools → Network → Disable cache and reload). The site should reflect whatever is in `docs/index.html` on the selected branch.
