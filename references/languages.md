---
title: Languages
description: Change the language of the API.
---

All the information returned by the API such as error messages or element JSON names are returned in English by default and this option can't be changed.&#x20;

However, the information returned in:

* Sport names.
* League names.
* Country names.
* Team names.

Since most of leagues, and teams share the same name among different languages, this isn't a thing you shouldn't worry as long as you keep their IDs.

However, we have different language options available and the API will be able to return the information in your preferred language.

To achieve this, you may specific your preferred language with the Accept-Language HTTP header:

{%hint danger%}
Don't use regional variants as it might not be available. Don't use multiple preferred languages or weighted multitypes.
{%endhint%}

| Header          | Value                                                                                                                                                                                        |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Accept-Language | <p><a href="https://es.wikipedia.org/wiki/ISO_639-1">ISO 639-1</a> code for your preffered language. </p><p></p><p>Valid options at the moment are "es" for Spanish or "en" for English.</p> |

{%hint warning%}
If the language you set is not valid or not available, no errors will be thrown and the locales will be returned in English by default as fallback.&#x20;

Make sure you use the correct language code!
{%endhint%}