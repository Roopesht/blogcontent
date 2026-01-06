# Sample Content for Ojasa Mirai Blog

This folder contains sample blog articles to demonstrate the blog platform functionality.

## Structure

```
sample-content/
├── index.json                          # Article manifest/index
├── README.md                           # This file
└── blogs/
    ├── welcome-to-ojasa-mirai/
    │   └── index.json                  # Article content
    ├── ai-roadmap-2025/
    │   └── index.json
    ├── getting-started-with-llms/
    │   └── index.json
    ├── prompt-engineering-guide/
    │   └── index.json
    ├── industry-trends-2025/
    │   └── index.json
    └── building-first-chatbot/
        └── index.json
```

## Article Format

Each article folder contains an `index.json` file with the following structure:

```json
{
  "slug": "article-url-slug",
  "title": "Article Title",
  "excerpt": "Brief description (160 chars)",
  "content": "Full HTML content of the article",
  "category": "Category Name",
  "tags": ["tag1", "tag2"],
  "author": "Author Name",
  "authorBio": "Author biography",
  "publishedAt": "2025-01-01T00:00:00Z",
  "updatedAt": "2025-01-01T00:00:00Z",
  "readTime": "X min",
  "featured": true/false,
  "popular": true/false,
  "seo": {
    "metaTitle": "SEO title",
    "metaDescription": "SEO description",
    "keywords": ["keyword1", "keyword2"]
  }
}
```

## Adding New Articles

To add a new article:

1. Create a new folder in `blogs/` with your article slug
2. Create an `index.json` file with the article data
3. Add the article entry to the main `index.json` file
4. (Optional) Add a `hero.jpg` image for the article

## Categories

Available categories:
- Career Advice
- Getting Started
- Project Tutorials
- Industry Trends

## Using Real Content

To use this with a real GitHub repository:

1. Create a public GitHub repository
2. Use the same folder structure
3. Update the `.env` file with your repository URL:
   ```
   VITE_CONTENT_REPO_URL=https://raw.githubusercontent.com/your-org/blog-content/main
   ```

## Image Handling

Hero images can be:
- Hosted on your GitHub repo: `https://raw.githubusercontent.com/.../hero.jpg`
- External URLs (Unsplash, etc.)
- Local files in the article folder

## Sample Articles Included

1. **Welcome to Ojasa Mirai** - Introduction to the blog
2. **AI Roadmap 2025** - Career guidance for AI developers
3. **Getting Started with LLMs** - Introduction to Large Language Models
4. **Prompt Engineering Guide** - Master prompt engineering techniques
5. **AI Industry Trends 2025** - Latest trends in AI development
6. **Building Your First Chatbot** - Step-by-step chatbot tutorial

All articles include rich, detailed content to showcase the blog's capabilities.

## Notes

- Content is written in HTML format
- Code blocks use `<pre><code>` tags
- Images in content should use full URLs
- Reading time is manually set but could be auto-calculated
