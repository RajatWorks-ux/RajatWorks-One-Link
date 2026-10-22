# RajatWorks — One-Link Router

This static entry point selects an existing portfolio based on the viewport and device signals:

- Desktop-sized viewport (> 1024 CSS px): the 3D desktop experience.
- Phone/tablet signals or viewport width <= 1024 CSS px: the cinematic phone/tablet experience.
- iPadOS desktop-mode tablets are additionally detected using touch points.
- Optional `?view=desktop` or `?view=mobile` query parameter is available for manual QA.

## Configure the target URLs

Edit the `TARGETS` object in `index.html` before deploying if the current portfolio deployment URLs have changed:

- Desktop: `https://rajatworks-ux.vercel.app/`
- Phone/tablet: `https://rajatworks1.vercel.app/`

These URLs were taken from the supplied projects' metadata. Their live status has not been verified in this environment.

## Deploy

Deploy this folder as a static site to the one public domain you want to share. The two portfolio applications remain independently deployed and maintain their own build/dependency trees. Share the router domain as the single entry link.

The selection is made on entry. Because the router redirects to a separate origin, changing the browser width after navigation will not automatically switch origins; live switching after resize would require a same-origin reverse proxy/path deployment and platform-specific configuration. Opening the link in a narrow laptop window will select the phone/tablet portfolio.

## Important

This router does not combine the two applications into one server, and it does not replace backend configuration for the Next.js application. Keep both original project license files and required notices. Confirm you have permission to publish all reused code, design, and media before deployment.
