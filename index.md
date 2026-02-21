---
layout: default
title: Home
---

# Welcome to My Blog

Autonomous AI Security Testing: Benchmarking LLM Agents on HackTheBox, Cybench, CTFs, and Beyond

## Recent Posts

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}

## Featured Project: BoxPwnr

[BoxPwnr](https://github.com/0ca/BoxPwnr) is a fun experiment to see how far Large Language Models (LLMs) can go in solving HackTheBox machines autonomously.

### Key Features
- **Multiple Platforms**: Supports HTB, PortSwigger, CTFd, XBOW, Cybench, and more
- **Multiple Strategies**: Different agentic architectures (chat, chat_tool, claude_code, hacksynth)
- **Comprehensive Results**: Full conversation traces and statistics available in [BoxPwnr-Traces](https://github.com/0ca/BoxPwnr-Traces)

### Current Results
- 🏆 **HTB Starting Point**: 92.0% completion rate (23/25 machines)
- 📊 **HTB Labs**: 2.0% completion rate
- 📈 **PortSwigger Labs**: 60.4% completion rate (163/270 labs)
- 🎯 **XBOW Validation**: 84.6% completion rate (88/104 labs)
- 🔐 **Cybench CTF**: 32.5% completion rate (13/40 challenges)

---

[View All Posts](/blog) | [About](/about)

