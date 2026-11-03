# Meilisearch application stack for Kubernetes on Wodby

Deploy the Meilisearch search engine on Kubernetes with Wodby.

This repository defines the Wodby stack manifests and default service
composition for Meilisearch.

<!-- wodby:generated:start -->

## Stack contract

- [Meilisearch stack on Wodby](https://wodby.com/stacks/meilisearch)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [Meilisearch service](https://github.com/wodby/service-meilisearch)

## What's included

| Component / service | Default configuration |
| --- | --- |
| Meilisearch<br>`meilisearch` | required; enabled by default |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->

## Connect to Meilisearch

Meilisearch answers at the `meilisearch` service's HTTPS domain. Use the generated master key in the service's
`MEILI_MASTER_KEY` variable to list API keys with `GET /keys`, then give frontends the **Default Search API Key**. See
the [service README](https://github.com/wodby/service-meilisearch#connect-to-meilisearch).

The default limits of 2 GiB memory and a 10 GiB volume suit small and medium indexes. Raise the memory limit for large
indexing batches and the volume for large datasets; dumps and snapshots are stored on the same volume.
