# Knowledge-Base
This is my public endpoint for all the notes that i expose to the world, It operates with mkdocs and every piece of knowledge that i wish to public from my second-brain-private project would reside here. 


# Setup

> Most of the steps are sourced from mkdocs-material documentation

1. Installed mkdocs and mkdocs-material
2. Yaml updation
    
```yaml
theme:
  name: material
```

3. Installed YAML extention from redhat, then opened settings `ctrl + ,` > settings > search for json > Edit in settings.json > replace the content with the following one:

```json
{
  "yaml.schemas": {
    "https://squidfunk.github.io/mkdocs-material/schema.json": "mkdocs.yml"
  },
  "yaml.customTags": [ 
    "!ENV scalar",
    "!ENV sequence",
    "tag:yaml.org,2002:python/name:materialx.emoji.to_svg",
    "tag:yaml.org,2002:python/name:materialx.emoji.twemoji",
    "tag:yaml.org,2002:python/name:pymdownx.superfences.fence_code_format"
  ]
}

```

4. We are trying and learning load balancing along the way, i would be using three different providers for this site. Cloudflare, Netlify and github pages.
5. Added custom js

```yaml
extra_javascript:
  - javascripts/extra.js
```