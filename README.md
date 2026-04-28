# yesterday-social-cdn

Public image CDN for Yesterday's social media posts.

Buffer's GraphQL API requires images to be reachable via public HTTPS URL. This repo serves as that public bucket — assets are pushed here, then the `raw.githubusercontent.com` URL is referenced in Buffer's `createPost` mutation.

## Structure

```
instagram/
  YYYY-MM-DD-slug/
    slide-01.png
    slide-02.png
    ...
```

Folder per scheduled post, named by post date + short slug.

## Notes

- **Public repository** — only post assets that are okay to be world-readable.
- All images already pass through Yesterday's blur step before landing here (personal data scrubbed).
- Old folders can be pruned after the post has been published — Buffer copies images to its own CDN at scheduling time.
