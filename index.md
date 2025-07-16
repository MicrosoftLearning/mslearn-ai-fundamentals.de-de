---
title: Microsoft Learn – Einführung in KI in Azure-Übungen
permalink: index.html
layout: home
---

# AI-900: Einführung in KI in Azure-Übungen

Diese Praxisübungen sind dafür konzipiert, die Schulungsinhalte auf [Microsoft Learn](https://docs.microsoft.com/training/) zu ergänzen.

Sie benötigen ein Microsoft Azure-Abonnement für diese Übungen. Sie können sich unter [https://azure.microsoft.com](https://azure.microsoft.com) für eine kostenlose Testversion registrieren.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
| Übungen |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
