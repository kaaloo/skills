# AI News Sources

This file documents the default sources used by the `ai-news` skill. Edit `fetch-news.ts` to add, remove, or swap sources.

## RSS Feeds

| Name | URL | Notes |
|------|-----|-------|
| Hugging Face Blog | https://huggingface.co/blog/feed.xml | Model releases, research, tutorials |
| VentureBeat AI | https://venturebeat.com/category/ai/feed/ | Industry news, funding, products |
| The Verge AI | https://www.theverge.com/rss/ai-artificial-intelligence/index.xml | Consumer AI, policy, culture |
| MIT Tech Review AI | https://www.technologyreview.com/feed/ | Research-leaning tech journalism |
| Ars Technica AI | https://feeds.arstechnica.com/arstechnica/index | Technical depth, policy |
| OpenAI Blog | https://openai.com/blog/rss/ | First-party OpenAI announcements |
| Google DeepMind Blog | https://deepmind.google/blog/rss.xml | First-party DeepMind research |
| Anthropic News | https://www.anthropic.com/rss.xml | First-party Anthropic announcements |

### Adding More RSS Feeds

Any standard RSS/Atom feed URL works. Good candidates:
- `https://arxiv.org/rss/cs.AI` — arXiv CS.AI preprints (high volume)
- `https://arxiv.org/rss/cs.LG` — arXiv Machine Learning
- `https://www.import.ai/feed` — Jack Clark's Import AI newsletter
- `https://lastweekin.ai/feed` — Last Week in AI recap

## YouTube Channels

Fetched via YouTube's public channel RSS feed (no API key required):
`https://www.youtube.com/feeds/videos.xml?channel_id=CHANNEL_ID`

| Name | Channel ID | Focus |
|------|-----------|-------|
| Yannic Kilcher | UCZHmQk67mSJgfCCTn7xBfew | Paper walkthroughs, ML research deep dives |
| Two Minute Papers | UCbfYPyITQ-7l4upoX8nvctg | Research paper summaries |
| AI Explained | UCNJ1Ymd5yFuUPtn21xtRbbw | Accessible AI news and model breakdowns |
| Matthew Berman | UCQgB5j8JONFTGRlCyxgUoqw | AI tools, product launches, demos |
| Andrej Karpathy | UCXUPKJO5MZQRRJECM5OI9ZA | Deep technical ML education |

### Finding Channel IDs

To find a channel's ID:
1. Go to the channel page on YouTube
2. View page source and search for `"channelId"`
3. Or use: `https://www.youtube.com/@handle` → check the URL after redirect, or use a tool like `https://commentpicker.com/youtube-channel-id.php`

## Transcript Availability

YouTube transcripts are fetched via `fetch-transcript.ts`. They are available when:
- The video has auto-generated captions (most English videos do)
- The creator has uploaded manual captions

Transcripts are NOT available for:
- Live streams (until archived)
- Shorts (usually)
- Videos where the creator has disabled captions
