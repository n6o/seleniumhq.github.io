---
title: "Téléchargement de fichier"
linkTitle: "Téléchargement de fichier"
weight: 2
aliases: ["/documentation/fr/worst_practices/file_downloads/"]
---

{{% pageinfo color="warning" %}}
<p class="lead">
   <i class="fas fa-language display-4"></i> 
   Page being translated from 
   English to French. Do you speak French? Help us to translate
   it by sending us pull requests!
</p>
{{% /pageinfo %}}

Bien qu'il soit possible de démarrer un téléchargement
en cliquant sur un lien avec un navigateur 
sous le contrôle de Selenium,
l'API n'expose pas la progression du téléchargement,
ce qui n'est pas idéal pour tester les fichiers téléchargés.
En effet, le téléchargement de fichiers n'est pas 
considéré comme un aspect important
d'émuler l'interaction des utilisateurs avec la plate-forme Web.
À la place, recherchez le lien à l'aide de Selenium
(et tous les cookies requis)
et le passer à une bibliothèque de requêtes HTTP comme
[libcurl](//curl.haxx.se/libcurl/).

The [HtmlUnit driver](https://github.com/SeleniumHQ/htmlunit-driver) can download 
attachments by accessing them as input streams by implementing the 
[AttachmentHandler](https://htmlunit.sourceforge.io/apidocs/com/gargoylesoftware/htmlunit/attachment/AttachmentHandler.html) 
interface. The AttachmentHandler can the be added to the [HtmlUnit](https://htmlunit.sourceforge.io/) WebClient.
