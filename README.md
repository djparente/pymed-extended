> This is a fork of gijswobben's excellent PyMed library. Please see https://github.com/gijswobben/pymed for the original repository. I have made small edits to it to enable additional handling of structured abstracts. Please feel free to continue extending this fork under the original MIT license.
> - djparente@github

# Changes from the original PyMed library
The PyMed library has been extended. The main addition is the `getStructuredAbstractContent` method, which extracts structured abstract content from an XML element to provide a more extensive view of articles on PubMed. 

The `query` method in the `api.py` file has been tweaked to accept an optional `reldate` parameter. This addition introduces flexibility in terms of seeking out recent articles based on publication date.

In the `article.py` file, a `structuredAbstract` attribute is now included in the `PubMedArticle` class. This new attribute captures the structured abstract content of an article, giving users access to more in-depth information.

The `helpers.py` file now incorporates a method that follows the same name as `getStructuredAbstractContent`. This enables users to draw out the text content of structured abstracts from an XML element. This novel feature enriches the library's ability to manage and retrieve structured abstracts in a user-centric way.

The `README.md` file now indicates this PyMed library as a fork from the original work of gijswobben, acknowledging due credit.

(This summary of changes was created programatically by gpt-3.5-turbo-16k and gpt-4 with modifications by author for accuracy)


# PyMed - PubMed Access through Python
PyMed is a Python library that provides access to PubMed through the PubMed API.

## Why this library?
The PubMed API is not very well documented and querying it in a performant way is too complicated and time consuming for researchers. This wrapper provides access to the API in a consistent, readable and performant way.

## Features
This library takes care of the following for you:

- Querying the PubMed database (with the standard PubMed query language)
- Batching of requests for better performance
- Parsing and cleaning of the retrieved articles

## Examples
For full (working) examples have a look at the `examples/` folder in this repository. In essence you only need to import the `PubMed` class, instantiate it, and use it to query:

```python
from pymed import PubMed
pubmed = PubMed(tool="MyTool", email="my@email.address")
results = pubmed.query("Some query", max_results=500)
```

## Notes on the API
The original documentation of the PubMed API can be found here: [PubMed Central](https://www.ncbi.nlm.nih.gov/pmc/tools/developers/). PubMed Central kindly requests you to:

> - Do not make concurrent requests, even at off-peak times; and
> - Include two parameters that help to identify your service or application to our servers
>   * _tool_ should be the name of the application, as a string value with no internal spaces, and
>   * _email_ should be the e-mail address of the maintainer of the tool, and should be a valid e-mail address.

## Notice of Non-Affiliation and Disclaimer 
The author of this library is not affiliated, associated, authorized, endorsed by, or in any way officially connected with PubMed, or any of its subsidiaries or its affiliates. The official PubMed website can be found at https://www.ncbi.nlm.nih.gov/pubmed/.
