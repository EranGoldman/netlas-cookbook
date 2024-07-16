

<div align="center">
      <img align="center" src="https://app.netlas.io/static/media/logo-dark.e3792204ae117bd83067f342f15944f6.svg" width="180px" >
     <h1>Welcome to Netlas CookBook!</h1>
     <img alt="GitHub stars" src="https://img.shields.io/github/stars/netlas-io/netlas-cookbook"> 
     <img alt="GitHub forks" src="https://img.shields.io/github/forks/netlas-io/netlas-cookbook"> <br>
     <img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat">
      <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fnetlas-io%2Fnetlas-cookbook&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false"/>
     <br>
     <br>
  The goal of this guide is very simple - to teach anyone interested in cyber security, regardless of their knowledge level, how to make the most of Netlas.io.
      <br>
     <br>
  ⭐️ Give us a star to show your appreciation <br>
  👁️ Subscribe for updates<br>
</div>






# Table of contents

- [What is Netlas.io?](#what-is-netlasio)
- [Simple usage examples](#simple-usage-examples) 
  - [Getting information about IP or domain](#getting-information-about-ip-or-domain)
  - [Search for non-latin domains](#search-for-non-latin-domains)
  - [Looking for websites that contain a certain word in their title](#looking-for-websites-that-contain-a-certain-word-in-their-title)
- [Search query syntax](#search-query-syntax)
  - [Filters (Fields)](#filters-fields)
  - [Logical operators](#logical-operators)
  - [Ranges](#ranges)
  - [Wildcards](#wildcards)
  - [Fuzzines](#fuzziness)
  - [Regular expressions](#regular-expressions)
  - [Other Netlas.io search features](#other-netlasio-search-features) 
- [API requests](#api-requests)
  - [How to find the API key](#how-to-find-the-api-key)
  - [Tools for debugging API requests](#tools-for-debugging-api-requests)
  - [Structure of Netlas API JSON response](#structure-of-netlas-api-json-response)
  - [Tools for working with data in JSON format](#tools-for-working-with-data-in-json-format)
  - [Netlas Python Library](#netlas-python-library)
  - [Examples of response keys for getting useful data](#examples-of-response-keys-for-getting-useful-data)
  - [Netlas Python response datatypes](#netlas-python-response-datatypes)
  - [Netlas CLI Tools](#netlas-cli-tools)
  - [Search vs Downloads vs Host methods](#search-vs-download-vs-host-methods)
  - [Additional request parameters](#additional-request-parameters)
  - [Make requests with Python (without Netlas Python Library](#make-requests-with-python-without-netlas-python-library)
  - [Examples for other programming languages](#examples-for-other-programming-languages)
     - [NodeJS](#nodejs)
     - [Ruby](#ruby)
     - [Bash](#bash)
  - [JQ Utility](#jq-utility)
  - [AI tools for writing code](#ai-tools-for-writing-code)
  - [Code checkers](#code-checkers)
 - [Using Netlas.io for OSINT](#using-netlasio-for-osint-open-source-intelligence)
   - [Search person's nickname or email in WHOIS contacts](#search-persons-nickname-or-email-in-whois-contacts)
   - [Search person's nickname or email in title and body of web page](#search-persons-nickname-or-email-in-title-and-body-of-web-page)
   - [Search links to "juicy info files" on subdomains of the company's website](#search-links-to-juicy-info-files-on-subdomains-of-the-companys-website)
   - [Phone number mentions search](#phone-number-mentions-search)
   - [Search file mentions (looking for content that may be infringing on copyrights)](#search-file-mentions-looking-for-content-that-may-be-infringing-on-copyrights)
   - [Domain WHOIS information gathering](#domain-whois-information-gathering)
   - [Search location in \<address\> tag](#search-location-in-address-tag)
   - [Search author name in meta tags](#search-author-name-in-meta-tags)
   - [What other interesting things can be found in the meta tags of html documents?](#what-other-interesting-things-can-be-found-in-the-meta-tags-of-html-documents)
   - [Search by FTP server's banners text](#search-by-ftp-servers-banners-text)
   - [Search for contact information in SSL certificates](#search-for-contact-information-in-ssl-certificates)
   - [Using Netlas as an alternative to the WayBack Machine](#using-netlas-as-an-alternative-to-the-wayback-machine)
   - [9 ways to search related websites](#9-ways-to-search-related-websites)
 - [Scraping (extract data from web page body)](#scraping-extract-data-from-web-page-body)
   - [Beatifulsoup package](#beatifulsoup-package)
   - [Re package](#re-package)
   - [Other Python packages for scraping](#other-python-packages-for-scraping)
 - [Using Netlas.io for Crypto Investigations](#using-netlasio-for-crypto-investigations)
    - [Search mining farms](#search-mining-farms)
    - [Search for websites infected with cryptominers](#search-for-websites-infected-with-cryptominers)
    - [Search vulnerable Bitcoin nodes](#search-vulnerable-bitcoin-nodes)
 - [Using Netlas.io for Pentest](#using-neltas-for-pentest)
    - [Search subdomains](#search-subdomains)
    - [Search for sites with specific vulnerabilities](#search-for-sites-with-specific-vulnerabilities)
    - [Search for sites with vulnerabilities that contain a certain word in their descriptions](#search-for-sites-with-vulnerabilities-that-contain-a-certain-word-in-their-descriptions)
    - [Search by server http header](#search-by-server-http-header)
      - [Default logins and passwords](#default-logins-and-passwords)
    - [Search servers with CVEs by favicon hash](#search-servers-with-cves-by-favicon-hash)
    - [Search servers with CVEs by tag name](#search-servers-with-cves-by-tag-name)
    - [Search vulnerable servers and devices near you (or any other location)](#search-vulnerable-servers-and-devices-near-you-or-any-other-location)
    - [Search for login/admin panels](#search-for-loginadmin-panels)
    - [Search for vulnerable database admin panels](#search-for-vulnerable-database-admin-panels)
    - [Search for sites vulnerable to SQL injection](#search-for-sites-vulnerable-to-sql-injection)
- [IoT search: 9 basic ways](#iot-search-9-basic-ways)
    - [Search by http.title](#search-by-httptitle)
    - [Search by http.body](#search-by-httpbody)
    - [Search by port](#search-by-port)
    - [Search by banner](#search-by-banner)
    - [Search by favicon](#search-by-favicon)
    - [Search by server headers](#search-by-server-headers)
    - [Search by cookies](#search-by-cookies)
    - [Search by tag](#search-by-tag)
    - [Additional search filters](#additional-search-filters)
- [Using Netlas.io for Darknet research](#using-netlasio-for-darknet-research)
    - [Tor exit nodes search](#tor-exit-nodes-search)
    - [Collecting links to .onion sites](#collecting-links-to-onion-sites)
- [Files, backups and logs directories search](#files-backups-and-logs-directories-search)
- [Using Netlas.io for Digital Forensics and Incident Response](#using-netlasio-for-digital-forensics-and-incident-response)         
    - [SMTP servers information gathering](#smtp-servers-information-gathering)
    - [Search for domains that could potentially be used for phishing](#search-for-domains-that-could-potentially-be-used-for-phishing)
    - [Favicon search](#favicon-search)
    - [Search for domains associated with a specific subnet](#search-for-domains-associated-with-a-specific-subnet)
    - [Search for servers with malicious software](#search-for-servers-with-malicious-software)
- [Search for technologies and code examples](#search-for-technologies-and-code-examples)
- [Using Netlas.io for fun or netstalking](#using-netlasio-for-fun-or-netstalking
)
- [Common problems](#common-problems)
     - [Error 429 - Too frequent requests](#error-429---too-frequent-requests)
     - [KeyError](#keyerror)
     - [Automation of work with the list of requests](#automation-of-work-with-the-list-of-requests)
     - [Saving data in CSV format](#saving-data-in-csv-format)
     - [Saving data in other formats](#saving-data-in-other-formats)
     - [Decoding Punycode domains](#decoding-punycode-domains)
     - [What to do if search queries don't return results?](#what-to-do-if-search-queries-dont-return-results)
     - [Removing html tags from http body](#removing-html-tags-from-http-body)
     - [Working with very large amounts of data](#working-with-very-large-amounts-of-data)


# What is Netlas.io?


Search engine to find and analyse information about all IP addresses and domains available on the Internet. Netlas has some attack surface management features, but this guide is focused mostly on Netlas search tools and how to use them in automations.

Netlas.io includes several search tools:


- **IP/Domain info** [→](https://app.netlas.io/host/)   
- **Response search** [→](https://app.netlas.io/responses/)  
- **DNS search** [→](https://app.netlas.io/domains/)   
- **IP WHOIS search** [→](https://app.netlas.io/whois_ip/)   
- **Domain WHOIS search** [→](https://app.netlas.io/whois_domains/)   
- **Certificates search** [→](https://app.netlas.io/certs/)  



Surface management tools are in development:

- **Attack Surface Discovery Tool** [→](https://app.netlas.io/asd/)  

  
Some of the databases collected by Netlas.io can be purchased from the **Datastore** [→](https://app.netlas.io/datastore/)  

You can also integrate Netlas.io services into your applications using **API** [→](https://docs.netlas.io/automation/)  

You can read short articles about main use-cases here:

- [Attack Surface Discovery](https://netlas.io/use-cases/attack_surface_discovery)
- [Non-intrusive security assessment](https://netlas.io/use-cases/security-assessment)
- [Uncover shadow IT and phishing threats using](https://netlas.io/use-cases/shadow-it-and-phishing-threats)
- [OSINT investigations](https://netlas.io/use-cases/osint_investigations)
- [Vulnerable devices search](https://netlas.io/use-cases/vulnerable_devices)
- [Security of IoT & industrial devices](https://netlas.io/use-cases/industrial-security)
- [Reputation scoring](https://netlas.io/use-cases/reputation_scoring)
- [Threat hunting](https://netlas.io/use-cases/threat_hunting)


# Simple usage examples


Before we get into the technical details, let's see how [Netlas.io](https://app.netlas.io/) works with a few simple examples.


## Getting information about IP or domain
![Domain information gathering](images/domain_information_gathering.png)


Open [Netlas.io IP/Domain info](https://app.netlas.io/host/netlas.io/) and enter the domain name or IP. The following information will be displayed as a result:

* whois data (registrant, location, emails, phones)
* related domains
* MX and NS records
* exposed ports & software (sometimes additionally displays information about vulnerabilities)




## Search for non-latin domains

![Punycode convert](images/punycode_convert.png)

If you need to find Chinese or other internationalised domain names, then convert them to Punycode. For example:

```
domain:*.xn--fiqs8s
```

You can do this with the help of special online tools. For example - [Charset.org](https://www.charset.org/punycode)



## Looking for websites that contain a certain word in their title



![Search by http title](images/http_title_simple_example.png)


Open [Netlas.io response search](https://app.netlas.io/responses/) and enter:



```
http.title:g*thub
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3Ag*thub&page=1&indices=)


This will find all servers whose HTTP titles contain the word starts with "g" and ends to "thub". Read more about using asterisks below.





# Search query syntax


Now let's learn more about how search queries work in [Netlas.io](https://app.netlas.io/). 

Netlas.io based on [Elasticsearch](https://github.com/elastic/elasticsearch), free and open, distributed, RESTful search engine. And the search methods in Netlas.io are very similar to those of other Elasticsearch-based databases. 


## Filters (Fields)


![Search filters](images/search_filters.png)



Response, DNS, IP and Certificates search allow you to use filters (fields) in search queries. For example:


```
http.body:netlas
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.body%3Anetlas&page=1&indices=)

You can use this query to find pages which contain the word "netlas" inside their <body> html tag.


A list of available filters for each search type is displayed on the right side of the page.


![Filters Mapping Images](images/filters.png)


Filters allow you to search for servers based on many different parameters. For example:


* domain
* ip
* protocol
* certificate
* cve
* geolocation (city, continent, country, lat and long)

and many others.



## Logical operators

You can use multiple filters in a single query and combine them using logical operators AND, OR, NOT. For example:


```
http.title:netlas NOT port:443
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3Anetlas%20NOT%20port%3A443&page=1&indices=)



If you want to combine multiple conditions in your query, use parentheses:



```
http.title:(netlas OR shodan) NOT port:443
```

[Try in Netlas](https://nt.ls/OrFOY)


## Ranges


If you use a numeric value as the value of a field, you can designate it as a value from and to (extreme limits of the value range):


```
ip:[173.194.222.0 TO 173.194.222.255] 
```


[Try in Netlas](https://app.netlas.io/responses/?q=ip%3A%5B173.194.222.0%20TO%20173.194.222.255%5D%20&page=1&indices=)



Or mark only the upper or only the lower limit of the value:


```
host:"1.1.1.1" port:<=1000
```

[Try in Netlas](https://app.netlas.io/responses/?q=host%3A%221.1.1.1%22%20port%3A%3C%3D1000&page=1&indices=)


## Wildcards


If you don't know the exact description of a certain character in your query (for example, you don't know the exact zone for a domain or the spelling of a name), you can replace it with an asterisk:


```
domain:google.*
```


[Try in Netlas](https://app.netlas.io/responses/?q=domain%3Agoogle.*&page=1&indices=)


You can also use question mark:


```
domain:google.?
```

[Try in Netlas](https://app.netlas.io/responses/?q=domain%3Agoogle.%3F&page=1&indices=)

Asterisk - many symbols, question mark - one symbol.


You can also use asterisks in filters. For example:

```
\*.banner:database
```

This query do a search on all banner types simultaneously and replaces several filters: amqp.banner:, ftp.banner:, dns.banner:, telnet.banner:, etc.


## Fuzziness

![Fuzzines](images/fuziness.png)

If you need to search not by exact, but by approximate value of a field (for example, pages whose titles contain all names consonant with Joseph), just add ~ to the query:


```
http.title:Joseph~
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3AJoseph~&page=1&indices=)

## Regular expressions


Regular expressions - it is a sequence of characters that allows you to search for, retrieve and replace pieces of text in a source document that match certain patterns. For example:

* ([a-zA-Z0–9+._-]+@[a-zA-Z0–9._-]+\.[a-zA-Z0–9_-]+) - any email address
* <.*?> - any html tag
* ^[\+]?[(]?[0-9]{3}[)]?[-\s\.]?[0-9]{3}[-\s\.]?c{4,6}$ - any phone number
* ^[\+]?[(]?[0-9]{3}[)]?[-\s\.]?[0-9]{3}[-\s\.]?[0-9]{4,6}$ - any Bitcoin address


For more information on using regular expressions, see the examples in the Netlas Cookbook (what you're reading now) and the links below:


[Regex Syntax Manual in Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/regexp-syntax.html)

[How regular expressions can be useful in OSINT. Theory and some practice using Google Sheets](https://medium.com/p/31d31efabd5)



## Other Netlas.io search features


### Download results

![Download results](images/download_results.png)

You can save your results (all or selected fields) in JSON and CSV format to view them in a format you like or automatically analyse them with different tools.


### Group results

![Group results](images/group_results.png)


You can group results by different field values to speed up the search time. For example, by domain name or geolocation.


### Share results

![Share results](images/share_results.png)

You can freely share links to search results (no registration is required to open them, unless the user has exceeded the free limit of 50 requests).

### Search history

![Request history](images/request_history.png)


Also remember that all the quiries you have made can be viewed on your profile page (link in the top right corner).


# API requests


Netlas.io's most important function is to help people conduct cybersecurity research faster and more efficiently. The service has an API (application programming interface) that allows you to automate the execution of various requests. 

It can be implemented both in simple Python or Bash scripts of a few lines in length and in complex multifunctional applications.


You can read more about using the Netlas API in the Netlas Cookbook (what you're reading now) or in the official documentation:


[API Documentation](https://netlas-api.readthedocs.io/en/latest/)


## How to find the API-key?


This is the very first place to start with the API. You don't even have to pay for a subscription (50 requests per day are free). Just go to [profile page](https://app.netlas.io/profile/).



![Profile page](images/profile.png)

## Tools for debugging API requests

![Netlas shema](images/netlas_shema.png)


You don't have to write scripts or create applications to start using the Netlas API. You can simply test it using our online tool [Netlas schema](https://app.netlas.io/schema).


Firstly, click "Authorize" and enter API key. Secondly, select API method, click "Try it out/", enter search query (and other parameters) and click "Execute".



Netlas scheme is still under development and you may find its analogs designed for testing different APIs more convenient:

[Reqbin](https://reqbin.com/)

[ExtendClass Online Rest Client](https://extendsclass.com/rest-client-online.html)





## Structure of Netlas API JSON response 

![JSON API response](images/json_api_response.png)


Similar to other APIs, the Netlas API response consists of headers and a response body in JSON (JavaScript Object Notation) format. JSON files contain data in key-value format and can be analysed using almost any programming language.


If you use Netlas Shema, you can copy or download the response body and view it in any text editor or JSON analyser.


## Tools for working with data in JSON format

![JSON Eveluator](images/json_evaluator.png)


A little tip that will come in handy when writing code using the Netlas API. In order to understand the structure of a JSON file faster and find the path to get a certain value, use special tools such as:

[JSON Path Online Evaluator](https://jsonpath.com)


[JSON Path Finder](https://jsonpathfinder.com)



## Netlas Python library



The easiest way to automate requests to the Netlas API is to use a specially designed Python library (package).


[Netlas-Python library Github repo](https://github.com/netlas-io/netlas-python)

[Netlas Python Library Documentation](https://netlas-python.readthedocs.io/en/latest/)


Let's see how it works with a simple example. All code samples from Netlas Cookbook are located in the **scripts** folder. You can clone this repository and run them on your device:


```shell
git clone https://github.com/netlas-io/netlas-cookbook
```


If you haven't run a Python scripts before today and don't know how to do it, you can start by open Netlas CookBook repository in Gitpod.
Gitpod is a cloud development environment based on Ubuntu (Linux distribution). Just open this link in your browser (log in with your Github account):

[Run Netlas Cookbook in Gitpod](https://gitpod.io#https://github.com/netlas-io/netlas-cookbook)


![Netlas Github](images/netlas_python_example_py.png)


Install Netlas Python library using pip (package installer for Python). Enter in the command line:


```shell
pip install netlas

```

Check the installation. Enter in the command line:

```shell
netlas --help
```

Run netlas_python_example.py:


```shell
python scripts/netlas_python_example.py:
```



And of course, you can just copy the code and save to files. Here is the code of the first example:


```python
import netlas

apikey = "YOUR API KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `port:7001`
netlas_query = netlas_connection.query(query="port:7001")

# iterate over data and print: IP address, port, path and protocol
for response in netlas_query['items']:
    print(f"{response['data']['ip']}:{response['data']['port']}{response['data']['path']} [{response['data']['protocol']}]")

```

## Examples of response keys for getting useful data


It's mentioned above that in order to find JSON patches of API response to get the data you need, you can use special online applications (JSON-evaluators). To make your life even better, here is a small list of examples of Python library response keys that are needed most often.


```python


# Main domain/ip info

response['data']['uri']
response['data']['ip']
response['data']['http']['title']
response['data']['http']['meta']
response['data']['http']['body']



# Geo info


response['data']['geo']['continent']
response['data']['geo']['country']
response['data']['geo']['city']
response['data']['geo']['location']['lat']
response['data']['geo']['location']['long']


# Whois geo info

response['data']['whois']['net']['country']
response['data']['whois']['net']['address']
response['data']['whois']['net']['city']
response['data']['whois']['net']['contacts']['emails']
response['data']['whois']['net']['contacts']['phones']



# Http status and favicon ico info

response['data']['port']
response['data']['http']['status_code']
response['data']['http']['status_line']
response['data']['http']['favicon']['image']
response['data']['http']['favicon']['path']


# Basic CVE info 

response['data']['cve'][0]['name']
response['data']['cve'][0]['description']
response['data']['cve'][0]['base_score']
response['data']['cve'][0]['has_exploit']
response['data']['cve'][0]['exploit_links']

```






## Netlas Python response datatypes

![Python Netlas datatypes](images/datatypes.png)

When working with the Netlas Python Library, it is very important to correctly specify the type of data you want to retrieve. By default, the response type is returned and many Netlas CookBook examples use it.

But for some tasks, like getting whoois information about a domain or searching for domains in a subnet you need to use a different data type. For example:


```
netlas_query = netlas_connection.query(query='a:"163.114.132.0/24"',datatype="domain")
```


If you think some query is not returning results when it should - just try changing the value of the **datatype** parameter. It is very likely that this will help.

Now let's look at examples of what types of data can be retrieved using the Netlas Python Library.


### datatype="response"


Corresponds to the results that can be obtained in [Netlas Response Search](https://app.netlas.io/responses/).


```
{
    "last_updated": "2023-09-23T04:39:09.622Z",
    "jarm": "29d29d15d29d29d21c29d29d29d29d935576741dfb52d851054f608b751a40",
    "isp": "Amazon.com",
    "ip": "15.185.166.67",
    "certificate": {
        "issuer_dn": "CN=Amazon RSA 2048 M01, O=Amazon, C=US",
        "fingerprint_md5": "8f4fd5fc8311e5edf02db7ef94eca174",
        "chain": [
            {
                "issuer_dn": "CN=Amazon Root CA 1, O=Amazon, C=US",
                "fingerprint_md5": "943b3cc1d311e06f4e4acbf58f289ad2",
                "redacted": False,
                "signature": {
                    "valid": False,
                    "signature_algorithm": {
                        "name": "SHA256-RSA",
                        "oid": "1.2.840.113549.1.1.11",
                    },
                    "self_signed": False,
                    "value": "rQDeAgUjLgYyYrRrsZQW5BFA3iv6WcE17+CqjytBudHzhzkAHfI9tadHDAYGxpHzB1cC1O29F8GQmr9IdaIHTzDdSmpCtQ09FcAP/oRbxjyZzFdSsdhuEtWWkpNLlOUH6ImCCGp6NNSeZOE9h2qSkJpjoUv4j7bqNNMFviDC3gbijJ9zi59NOYXKzhk2nYXJnsn4UD+2foih78qEBotQtApcphxE8f3IYUBg8mElqgf0x8JzdeQMC0KNBOVfREiZW3uJgZaniJ1LDWLoBMTX/rTosm3K7MAcvDhbHd+Fzlt640lLbLmn3fQFskmt4cUUa8LM681/1lhpusMgfn+wuA==",
                },
                "subject": {
                    "country": ["US"],
                    "organization": ["Amazon"],
                    "common_name": ["Amazon RSA 2048 M01"],
                },
                "serial_number": "166129328851546858514271303855646110030630415",
                "version": 3,
                "issuer": {
                    "country": ["US"],
                    "organization": ["Amazon"],
                    "common_name": ["Amazon Root CA 1"],
                },
                "tbs_noct_fingerprint": "0706b7e834d90e828da6e11374d1253e9254bd252349fd5cada87040945476b1",
                "fingerprint_sha256": "5338ebec8fb2ac60996126d3e76aa34fd0f3318ac78ebb7ac8f6f1361f484b33",
                "extensions": {
                    "subject_key_id": "81b80e638a891218e5fa3b3b50959fe6e5901385",
                    "crl_distribution_points": [
                        "http://crl.rootca1.amazontrust.com/rootca1.crl"
                    ],
                    "certificate_policies": [{"id": "2.23.140.1.2.1"}],
                    "authority_key_id": "8418cc8534ecbc0c94942e08599cc7b2104e0a08",
                    "key_usage": {
                        "digital_signature": True,
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 97,
                    },
                    "authority_info_access": {
                        "issuer_urls": [
                            "http://crt.rootca1.amazontrust.com/rootca1.cer"
                        ],
                        "ocsp_urls": ["http://ocsp.rootca1.amazontrust.com"],
                    },
                    "basic_constraints": {"max_path_len": 0, "is_ca": True},
                    "extended_key_usage": {"client_auth": True, "server_auth": True},
                },
                "tbs_fingerprint": "0706b7e834d90e828da6e11374d1253e9254bd252349fd5cada87040945476b1",
                "subject_dn": "CN=Amazon RSA 2048 M01, O=Amazon, C=US",
                "fingerprint_sha1": "2ad974a775f73cbdbbd8f5ac3a49255fa8fb1f8c",
                "signature_algorithm": {
                    "name": "SHA256-RSA",
                    "oid": "1.2.840.113549.1.1.11",
                },
                "spki_subject_fingerprint": "84d611e87c488631378a9a9aa87c77cc6b4b34243abf9e46c42113580dac3e27",
                "validity": {
                    "start": "2022-08-23T22:21:28Z",
                    "length": 252460800,
                    "end": "2030-08-23T22:21:28Z",
                },
                "validation_level": "DV",
            },
            {
                "issuer_dn": "CN=Starfield Services Root Certificate Authority - G2, O=Starfield Technologies\\, Inc., L=Scottsdale, ST=Arizona, C=US",
                "fingerprint_md5": "e865a22aae524d26869af0448d6fd896",
                "redacted": False,
                "signature": {
                    "valid": False,
                    "signature_algorithm": {
                        "name": "SHA256-RSA",
                        "oid": "1.2.840.113549.1.1.11",
                    },
                    "self_signed": False,
                    "value": "YjdCXLwQtT6LLOkMm2xF4gcAevnFWAu5CIw+7bMlPLVvUOTNNWqnkzSWMiGpSESrnO09tKpzbeR/FoCJbM8oAxiDR3mjEH4wW6w7sGDgd9QIpuEdfF7Au/maeyKdpwAJfqxGF4PcnCZXmTA5YpaP7dreqsXMGz7KQ2hsVxa81Q4gLv7/wmpdLqBKbRRYh5TmOTFffHPLkIhqhBGWJ6bt2YFGpn6jcgAKUj6DiAdjd4lpFw85hdKrCEVN0FE6/V1dN2RMfjCyVSRCnTawXZwXgWHxyvkQAiSr6w10kY17RSlQOYiypok1JR4UakcjMS9cmvqtmg5iUaQqqcT5NJ0hGA==",
                },
                "subject": {
                    "country": ["US"],
                    "organization": ["Amazon"],
                    "common_name": ["Amazon Root CA 1"],
                },
                "serial_number": "144918191876577076464031512351042010504348870",
                "version": 3,
                "issuer": {
                    "country": ["US"],
                    "province": ["Arizona"],
                    "organization": ["Starfield Technologies, Inc."],
                    "locality": ["Scottsdale"],
                    "common_name": [
                        "Starfield Services Root Certificate Authority - G2"
                    ],
                },
                "tbs_noct_fingerprint": "c95f7b20f6fcd39fd3a07a2e44252423b634fdbe35e1e045d964deea626115cb",
                "fingerprint_sha256": "87dcd4dc74640a322cd205552506d1be64f12596258096544986b4850bc72706",
                "extensions": {
                    "subject_key_id": "8418cc8534ecbc0c94942e08599cc7b2104e0a08",
                    "crl_distribution_points": [
                        "http://crl.rootg2.amazontrust.com/rootg2.crl"
                    ],
                    "certificate_policies": [{"id": "2.5.29.32.0"}],
                    "authority_key_id": "9c5f00dfaa01d7302b3888a2b86d4a9cf2119183",
                    "key_usage": {
                        "digital_signature": True,
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 97,
                    },
                    "authority_info_access": {
                        "issuer_urls": ["http://crt.rootg2.amazontrust.com/rootg2.cer"],
                        "ocsp_urls": ["http://ocsp.rootg2.amazontrust.com"],
                    },
                    "basic_constraints": {"is_ca": True},
                },
                "tbs_fingerprint": "c95f7b20f6fcd39fd3a07a2e44252423b634fdbe35e1e045d964deea626115cb",
                "subject_dn": "CN=Amazon Root CA 1, O=Amazon, C=US",
                "fingerprint_sha1": "06b25927c42a721631c1efd9431e648fa62e1e39",
                "signature_algorithm": {
                    "name": "SHA256-RSA",
                    "oid": "1.2.840.113549.1.1.11",
                },
                "spki_subject_fingerprint": "064778d61d47af9b3bf3cbd1dabc44c6575ab14d0be5b08461fc6ebeac97db18",
                "validity": {
                    "start": "2015-05-25T12:00:00Z",
                    "length": 713278800,
                    "end": "2037-12-31T01:00:00Z",
                },
                "validation_level": "unknown",
            },
            {
                "issuer_dn": "OU=Starfield Class 2 Certification Authority, O=Starfield Technologies\\, Inc., C=US",
                "fingerprint_md5": "c6150925cfea5941ddc7ff2a0a506692",
                "redacted": False,
                "signature": {
                    "valid": False,
                    "signature_algorithm": {
                        "name": "SHA256-RSA",
                        "oid": "1.2.840.113549.1.1.11",
                    },
                    "self_signed": False,
                    "value": "Ix3jilfKfekXeUzxHlX9zFNuPkcP38ZV8rIENu2AH1PEXTQoa77HVfxn6ss/f5CyM80bWBCCAvj4L/UTYNQFzvGBCMHdp3WXTxi5bd73k5EIun5ALO3B6rt2njMGdx0NCH9T3Rtkq4In8WnVTV6u9KHDdadYRC3yPHCYrLpptpV3fw8xXiz8oIc6R2nweV/0FFSklV4ReBJgJ86fwnf/I1N3Xbr/6lnn28+vkpbvJJo1EHqckcYOfZn2Pxnf9XJU4RWpB1l7g79SLkaMsgBkdhxI09h56G5WzK4sA5DXGTiZ5MoJGVv/B5awqH80Sd9WqfewX+0z7YxHtzADXfQDjA==",
                },
                "subject": {
                    "country": ["US"],
                    "province": ["Arizona"],
                    "organization": ["Starfield Technologies, Inc."],
                    "locality": ["Scottsdale"],
                    "common_name": [
                        "Starfield Services Root Certificate Authority - G2"
                    ],
                },
                "serial_number": "12037640545166866303",
                "version": 3,
                "issuer": {
                    "country": ["US"],
                    "organization": ["Starfield Technologies, Inc."],
                    "organizational_unit": [
                        "Starfield Class 2 Certification Authority"
                    ],
                },
                "tbs_noct_fingerprint": "8408d5e5010ab8da67eb33a7d79ace944dd0ac103ae6ead3ff30dec571066b03",
                "fingerprint_sha256": "28689b30e4c306aab53b027b29e36ad6dd1dcf4b953994482ca84bdc1ecac996",
                "extensions": {
                    "subject_key_id": "9c5f00dfaa01d7302b3888a2b86d4a9cf2119183",
                    "crl_distribution_points": ["http://s.ss2.us/r.crl"],
                    "certificate_policies": [{"id": "2.5.29.32.0"}],
                    "authority_key_id": "bf5fb7d1cedd1f86f45b55acdcd710c20ea988e7",
                    "key_usage": {
                        "digital_signature": True,
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 97,
                    },
                    "authority_info_access": {
                        "issuer_urls": ["http://x.ss2.us/x.cer"],
                        "ocsp_urls": ["http://o.ss2.us/"],
                    },
                    "basic_constraints": {"is_ca": True},
                },
                "tbs_fingerprint": "8408d5e5010ab8da67eb33a7d79ace944dd0ac103ae6ead3ff30dec571066b03",
                "subject_dn": "CN=Starfield Services Root Certificate Authority - G2, O=Starfield Technologies\\, Inc., L=Scottsdale, ST=Arizona, C=US",
                "fingerprint_sha1": "9e99a48a9960b14926bb7f3b02e22da2b0ab7280",
                "signature_algorithm": {
                    "name": "SHA256-RSA",
                    "oid": "1.2.840.113549.1.1.11",
                },
                "spki_subject_fingerprint": "49d851948bc94134d7b0d7db70db8a471a832fb089a6e2c49c1f41b22d2044b5",
                "validity": {
                    "start": "2009-09-02T00:00:00Z",
                    "length": 783279556,
                    "end": "2034-06-28T17:39:16Z",
                },
                "validation_level": "unknown",
            },
        ],
        "src": "https://15.185.166.67:443/",
        "redacted": False,
        "signature": {
            "valid": False,
            "signature_algorithm": {
                "name": "SHA256-RSA",
                "oid": "1.2.840.113549.1.1.11",
            },
            "self_signed": False,
            "value": "qARBGZAxC9/c0jTpNm8WGjK5ezIuby5bduqHoTNk6qdWVikG0IsL1ccW6AYbljH2rluTo7RCHvsbLhhUc5eWrB3r3fALYEo0denhmIHoMC6KlNfFnq7Ocmo+9WQH1slBdHeYwn/GkDh4Y8TeQRAHxK60kFdGlnIvdqVTRl+FLPdSPmDTXSKBEw3UKFsK4qkKHAz9kzOvYTfh9cPi+1xXvZEoxexKZ797+SkFizaGSMlRZ3vw/H+3u5NEZEci7W7ryUJxcWIEzgEAltiYIehGZgG1vID5yottdqjHLjOUuo1ZWuY4QMa+1dcWAPi4HTnNFwSmuUuurj2MhVF5tUjR7A==",
        },
        "subject": {"common_name": ["ecs-t.me-south-1.amazonaws.com"]},
        "serial_number": "7594487530256147170481808759715185448",
        "version": 3,
        "issuer": {
            "country": ["US"],
            "organization": ["Amazon"],
            "common_name": ["Amazon RSA 2048 M01"],
        },
        "tbs_noct_fingerprint": "f200e84b762cb204f35c2e584d862d4151f55e9eb5f84bd90788a0ee6d6e9bbd",
        "fingerprint_sha256": "e508abebeacadee987d3358d2814704c679ebcd288162daec1b00eed5c67ce24",
        "extensions": {
            "subject_key_id": "c04875daafea32cea4b445cd519feba2a6c55abd",
            "crl_distribution_points": ["http://crl.r2m01.amazontrust.com/r2m01.crl"],
            "certificate_policies": [{"id": "2.23.140.1.2.1"}],
            "authority_key_id": "81b80e638a891218e5fa3b3b50959fe6e5901385",
            "key_usage": {
                "digital_signature": True,
                "key_encipherment": True,
                "value": 5,
            },
            "subject_alt_name": {
                "dns_names": [
                    "ecs-t.me-south-1.amazonaws.com",
                    "*.ecs-t.me-south-1.vpce.amazonaws.com",
                ]
            },
            "signed_certificate_timestamps": [
                {
                    "log_id": "7s3QZNXbGs7FXLedtM0TojKHRny87N7DUUhZRnEftZs=",
                    "signature": "BAMARjBEAiAOVC948tZX1EOqmn5GZAkWX5bDg+XdAfV1IDGaAn0srAIgLlsYlEa3ASMja81lJ9vdTv51s6rtuxuqGUjaRlS2yBc=",
                    "version": 0,
                    "timestamp": 1679003882,
                },
                {
                    "log_id": "c9meiRtMlnigIH1HneayxhzQUV5xGSqMa4AQesF3crU=",
                    "signature": "BAMASDBGAiEAhozpK/Us5nSLmK8R02khEGty0fs4Om2f7zGb6HZdUI4CIQD52vRjACeRv/R7k8pLmcRv3s/59wFMKBA5bC11746CKA==",
                    "version": 0,
                    "timestamp": 1679003882,
                },
                {
                    "log_id": "SLDja9qmRzQP5WoC+p0w6xxSActW3SyB2bu/qznYhHM=",
                    "signature": "BAMARjBEAiAoDiU/x7FVl+YjFangUrJgJ2GDPH6gr0AIVBU6rPfdmwIgUacvoJQu2yuTniJKRDYBHP16m1N6LwRRiLtkjB8/qho=",
                    "version": 0,
                    "timestamp": 1679003882,
                },
            ],
            "authority_info_access": {
                "issuer_urls": ["http://crt.r2m01.amazontrust.com/r2m01.cer"],
                "ocsp_urls": ["http://ocsp.r2m01.amazontrust.com"],
            },
            "basic_constraints": {"is_ca": False},
            "extended_key_usage": {"client_auth": True, "server_auth": True},
        },
        "tbs_fingerprint": "3e47d1114cea3de3212384410a358d387c7babf9a900138316e43fd8875f7ddf",
        "subject_dn": "CN=ecs-t.me-south-1.amazonaws.com",
        "names": [
            "*.ecs-t.me-south-1.vpce.amazonaws.com",
            "ecs-t.me-south-1.amazonaws.com",
        ],
        "fingerprint_sha1": "aabe018d8f41b00c195ccb10d8c0a0b34ade599c",
        "signature_algorithm": {"name": "SHA256-RSA", "oid": "1.2.840.113549.1.1.11"},
        "spki_subject_fingerprint": "39312a7565efe0e3bfa6be02ce4c7e5d6e3b635f4f4c0375dd7f6a62bb3776ec",
        "validity": {
            "start": "2023-03-16T00:00:00Z",
            "length": 29635199,
            "end": "2024-02-21T23:59:59Z",
        },
        "validation_level": "DV",
    },
    "uri": "https://15.185.166.67:443/",
    "host_type": "ip",
    "prot7": "http",
    "target": {"ip": "15.185.166.67", "type": "ip"},
    "ptr": ["ec2-15-185-166-67.me-south-1.compute.amazonaws.com"],
    "geo": {
        "continent": "Asia",
        "country": "BH",
        "tz": "Asia/Bahrain",
        "location": {"accuracy": 1000, "lat": 26.0333, "long": 50.55},
    },
    "path": "/",
    "protocol": "https",
    "prot4": "tcp",
    "@timestamp": "2023-09-23T04:39:09.622Z",
    "whois": {
        "abuse": "abuse@amazonaws.com",
        "related_nets": [
            {
                "country": "BH",
                "address": "Arcapita Building No. 551, Road 4612, Block 346\nBahrain Bay, Manama Sea Front",
                "city": "Manama",
                "created": "2020-04-15",
                "description": "Amazon Data Services Bahrain",
                "range": "15.185.0.0 - 15.185.255.255",
                "handle": "NET-15-185-0-0-2",
                "organization": "Amazon Data Services Bahrain (AT-9051)",
                "name": "AMAZON-BAH",
                "start_ip": "15.185.0.0",
                "net_size": 65535,
                "cidr": ["15.185.0.0/16"],
                "state": "PostalCode:",
                "postal_code": "Country:        BH",
                "end_ip": "15.185.255.255",
                "updated": "2021-02-10",
                "contacts": {
                    "emails": ["amzn-noc-contact@amazon.com", "abuse@amazonaws.com"],
                    "phones": ["+1-206-555-0000"],
                },
            }
        ],
        "net": {
            "country": "US",
            "address": "410 Terry Ave N.",
            "city": "Seattle",
            "created": "2021-01-28",
            "description": "Amazon Technologies Inc.",
            "range": "15.179.0.0 - 15.188.255.255",
            "handle": "NET-15-179-0-0-1",
            "organization": "Amazon Technologies Inc. (AT-88-Z)",
            "name": "AT-88-Z",
            "start_ip": "15.179.0.0",
            "net_size": 655359,
            "cidr": [
                "15.179.0.0/16",
                "15.180.0.0/14",
                "15.184.0.0/14",
                "15.188.0.0/16",
            ],
            "state": "WA",
            "postal_code": "98109",
            "end_ip": "15.188.255.255",
            "updated": "2021-02-10",
            "contacts": {
                "emails": [
                    "aws-rpki-routing-poc@amazon.com",
                    "abuse@amazonaws.com",
                    "aws-routing-poc@amazon.com",
                    "amzn-noc-contact@amazon.com",
                ],
                "phones": ["+1-206-555-0000"],
            },
        },
        "asn": {
            "registry": "arin",
            "number": ["16509"],
            "country": "US",
            "name": "AMAZON-02",
            "cidr": "15.185.0.0/16",
            "updated": "2021-01-28",
        },
    },
    "port": 443,
    "host": "15.185.166.67",
    "iteration": "8",
    "http": {
        "headers": {
            "date": ["Sat, 23 Sep 2023 04:39:04 GMT"],
            "server": ["Server"],
            "content_type": ["text/html"],
            "connection": ["keep-alive"],
            "content_length": ["565"],
        },
        "status_code": 403,
        "body_sha256": "dde8e6ebf3d4b584e943c002257d1882b5fdff8d988dba30479c35cbf3cfe0f9",
        "http_version": {"major": 1, "minor": 1, "name": "HTTP/1.1"},
        "title": "403 Forbidden",
        "status_line": "403 Forbidden",
        "body": '<html>\r\n<head><title>403 Forbidden</title></head>\r\n<body bgcolor="white">\r\n<center><h1>403 Forbidden</h1></center>\r\n<hr><center>Server</center>\r\n</body>\r\n</html>\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n<!-- a padding to disable MSIE and Chrome friendly error page -->\r\n',
        "content_length": 565,
    },
    "scan_date": "2023-09-22",
}

```

### datatype="domain"


Corresponds to the results that can be obtained in [Netlas DNS search](https://app.netlas.io/domains/).

```
{
    "a": [
        "31.13.66.35",
        "157.240.26.35",
        "31.13.72.59",
        "157.240.221.35",
        "157.240.212.35",
        "185.60.219.35",
        "163.70.128.35",
        "89.208.50.56",
        "89.208.50.46",
        "185.89.218.12",
        "31.13.72.36",
        "157.240.238.53",
        "157.240.28.35",
        "31.13.84.36",
        "31.13.66.13",
        "157.240.252.35",
        "188.186.146.207",
        "157.240.0.35",
        "157.240.234.35",
        "157.240.210.35",
        "157.240.214.35",
    ],
    "txt": [
        "google-site-verification=A2WZWCNQHrGV_TWwKh6KHY90tY0SHZo_RnyMJoDaG0s",
        "google-site-verification=wdH5DTJTc9AYNwVunSVFeK0hYDGUIEOGb-RReU6pJlY",
        "v=spf1 redirect=_spf.facebook.com",
        "google-site-verification=sK6uY9x7eaMoEMfn3OILqwTFYgaNp4llmguKI-C3_iA",
        "zoom-domain-verification=a6c90d61-66ec-485c-9f3d-cce7036f01bb",
    ],
    "last_updated": "2023-09-07T16:31:15.683Z",
    "@timestamp": "2023-09-07T16:31:15.683Z",
    "level": 2,
    "zone": "com",
    "ns": [
        "d.ns.facebook.com",
        "a.ns.facebook.com",
        "c.ns.facebook.com",
        "b.ns.facebook.com",
    ],
    "domain": "facebook.com",
    "mx": ["smtpin.vvv.facebook.com"],
}
```

### datatype="domain-whois"


Corresponds to the results that can be obtained in [Netlas Domain Whois Search](https://app.netlas.io/whois_domains/).

```
{
    "referer": ["http://id.facebook.org:80/"],
    "last_updated": "2023-01-06T05:22:51.401Z",
    "isp": "Facebook",
    "ip": "157.240.222.35",
    "certificate": {
        "issuer_dn": "CN=DigiCert SHA2 High Assurance Server CA, OU=www.digicert.com, O=DigiCert Inc, C=US",
        "fingerprint_md5": "98ab77aa62edb573f62de255d57eb7a7",
        "chain": [
            {
                "issuer_dn": "CN=DigiCert High Assurance EV Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US",
                "fingerprint_md5": "aaee5cf8b0d8596d2e0cbe67421cf7db",
                "redacted": False,
                "signature": {
                    "valid": False,
                    "signature_algorithm": {
                        "name": "SHA256-RSA",
                        "oid": "1.2.840.113549.1.1.11",
                    },
                    "value": "GIqViQPmbd9c/B1o6kqPg9ZRL41rRBaerGP10m5shJmLqoFxhFvtNE6wt3mSKcwtgGrwjiDheaT+A0cT6vWGyllxffQElmvTWVg9/tMxJVwYOISj5p+C/YxbmDFOzXieGv2Fy0mq8ieLmXL8PqrVQQva1TahvxxuR0l/XtlIfAPZ/YtJoJgmQkDr1pIRpGQKV1TE9R3WAl5rrO7EgJoScvpWk9f/vzCFBjC/C39O/1cFnSTthcMr+6Z1qKwtFu99eSey68KdCwfqqoXTAaMgKEFZQyjSgeOq9ux7O3e2QGKABUFFAe8XBj7ewDObZ9NhLnKH5Gn8EgBXQB5w9R7JtA==",
                    "self_signed": False,
                },
                "subject": {
                    "country": ["US"],
                    "organization": ["DigiCert Inc"],
                    "common_name": ["DigiCert SHA2 High Assurance Server CA"],
                    "organizational_unit": ["www.digicert.com"],
                },
                "serial_number": "6489877074546166222510380951761917343",
                "version": 3,
                "issuer": {
                    "country": ["US"],
                    "organization": ["DigiCert Inc"],
                    "common_name": ["DigiCert High Assurance EV Root CA"],
                    "organizational_unit": ["www.digicert.com"],
                },
                "tbs_noct_fingerprint": "ac5d79b4a1e84b9ea1f7f72b022158540f37c8557fc99f0c08b37f670632a177",
                "fingerprint_sha256": "19400be5b7a31fb733917700789d2f0a2471c0c9d506c0e504c06c16d7cb17c0",
                "extensions": {
                    "subject_key_id": "5168ff90af0207753cccd9656462a212b859723b",
                    "crl_distribution_points": [
                        "http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl"
                    ],
                    "certificate_policies": [
                        {"cps": ["https://www.digicert.com/CPS"], "id": "2.5.29.32.0"}
                    ],
                    "key_usage": {
                        "digital_signature": True,
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 97,
                    },
                    "authority_key_id": "b13ec36903f8bf4701d498261a0802ef63642bc3",
                    "authority_info_access": {
                        "ocsp_urls": ["http://ocsp.digicert.com"]
                    },
                    "basic_constraints": {"max_path_len": 0, "is_ca": True},
                    "extended_key_usage": {"client_auth": True, "server_auth": True},
                },
                "tbs_fingerprint": "ac5d79b4a1e84b9ea1f7f72b022158540f37c8557fc99f0c08b37f670632a177",
                "subject_dn": "CN=DigiCert SHA2 High Assurance Server CA, OU=www.digicert.com, O=DigiCert Inc, C=US",
                "fingerprint_sha1": "a031c46782e6e6c662c2c87c76da9aa62ccabd8e",
                "signature_algorithm": {
                    "name": "SHA256-RSA",
                    "oid": "1.2.840.113549.1.1.11",
                },
                "spki_subject_fingerprint": "4d8f65901ef8a23b1210242a5dfc786708a0d4008e7cecd03d4145a1c0834095",
                "validity": {
                    "start": "2013-10-22T12:00:00Z",
                    "length": 473385600,
                    "end": "2028-10-22T12:00:00Z",
                },
                "validation_level": "unknown",
            }
        ],
        "redacted": False,
        "src": "https://id.facebook.org:443/",
        "signature": {
            "valid": False,
            "signature_algorithm": {
                "name": "SHA256-RSA",
                "oid": "1.2.840.113549.1.1.11",
            },
            "value": "J4KWSqUeBXSNTCAN0TB+tkpGu1GoAszD2KpmS0LXoUWz5ei2qdWQgTx2ev0z8yoDO1cCIM7VO89lazjpyF+XuwyMLnuYs9HfJpnAaeLnfPUY5ZDT+bVmqZY6Kldz5WE3DJHLx8PCpC2doO44NOU6A89HUJ8oOXB3rAXkC9rWaAwsbj0fxyHfv7U4mPMQIcbbK8S1Frj/x2+ti7VgywWZ9YvGY+kFdneSUL1TIrq05yktGmKp0D6lJjHgYUDcP9uOmHlwQcdmQceLjOZsne5F5CLUb5uxDBGvYW6vdyU9ludj5G3q8TxHzT7kA0ZEPXRT2E7zOusOqmk1SFDkqoZKjA==",
            "self_signed": False,
        },
        "subject": {
            "country": ["US"],
            "province": ["California"],
            "organization": ["Facebook, Inc."],
            "locality": ["Menlo Park"],
            "common_name": ["*.facebook.com"],
        },
        "serial_number": "19893338216669499980325027031545953435",
        "version": 3,
        "issuer": {
            "country": ["US"],
            "organization": ["DigiCert Inc"],
            "common_name": ["DigiCert SHA2 High Assurance Server CA"],
            "organizational_unit": ["www.digicert.com"],
        },
        "tbs_noct_fingerprint": "df456e6ceaa34418349216961cc6ecef01376a9e32c33721b1587cbf1c72197e",
        "fingerprint_sha256": "6d3310857228502a97dd41ed65e60b0010fadaf89dd3751f58afb4e7df1a6ab8",
        "extensions": {
            "subject_key_id": "4c15f24cbbc260120e4d70080d1bbb5dabe7c2c8",
            "crl_distribution_points": [
                "http://crl3.digicert.com/sha2-ha-server-g6.crl",
                "http://crl4.digicert.com/sha2-ha-server-g6.crl",
            ],
            "certificate_policies": [
                {"cps": ["http://www.digicert.com/CPS"], "id": "2.23.140.1.2.2"}
            ],
            "key_usage": {"digital_signature": True, "value": 1},
            "authority_key_id": "5168ff90af0207753cccd9656462a212b859723b",
            "subject_alt_name": {
                "dns_names": [
                    "*.facebook.com",
                    "*.facebook.net",
                    "*.fbcdn.net",
                    "*.fbsbx.com",
                    "*.m.facebook.com",
                    "*.messenger.com",
                    "*.xx.fbcdn.net",
                    "*.xy.fbcdn.net",
                    "*.xz.fbcdn.net",
                    "facebook.com",
                    "messenger.com",
                ]
            },
            "signed_certificate_timestamps": [
                {
                    "log_id": "6D7Q2j71BjUy51covIlryQPTy9ERa+zraeF3fW0GvW4=",
                    "signature": "BAMARzBFAiEAppvmXJDR1evBdQF5iyEXzzrAOcMQW2Fm/i9ViUFXl5MCICZdSiqRejoyhl8uNBBx5v5Cm1Pd85pFJKaDwonWPIZi",
                    "version": 0,
                    "timestamp": 1665797310,
                },
                {
                    "log_id": "s3N3B+GEUPhjhtYFqdwRCUp5LbFnDAuH3PADDnk2pZo=",
                    "signature": "BAMASDBGAiEAwQs698alQANUk0RinrEjZH3TMFrzADwVy0cPTOV/i8UCIQCYAmFDOK3MUylxldqK6AsFmXFYQZUf2Vh6OBf0Hh4eTw==",
                    "version": 0,
                    "timestamp": 1665797310,
                },
                {
                    "log_id": "tz77JN+cTbp18jnFulj0bF38Qs96nzXEnh0JgSXttJk=",
                    "signature": "BAMARzBFAiAlp5VSWNIfuPEqUaJM4KPYDTtV1NKLS9cQCZO+KbwubwIhAOtoFMwjvpXfo0lBEdGLv5Euz/cbvc9Vs0+rxGWKYmyX",
                    "version": 0,
                    "timestamp": 1665797310,
                },
            ],
            "authority_info_access": {
                "issuer_urls": [
                    "http://cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt"
                ],
                "ocsp_urls": ["http://ocsp.digicert.com"],
            },
            "basic_constraints": {"is_ca": False},
            "extended_key_usage": {"client_auth": True, "server_auth": True},
        },
        "tbs_fingerprint": "5fba091ad7823e298babad2664328d4d0ebe959672360389ba19a1407e729073",
        "subject_dn": "CN=*.facebook.com, O=Facebook\\, Inc., L=Menlo Park, ST=California, C=US",
        "names": [
            "*.facebook.com",
            "*.facebook.net",
            "*.fbcdn.net",
            "*.fbsbx.com",
            "*.m.facebook.com",
            "*.messenger.com",
            "*.xx.fbcdn.net",
            "*.xy.fbcdn.net",
            "*.xz.fbcdn.net",
            "facebook.com",
            "messenger.com",
        ],
        "fingerprint_sha1": "78e0341711b4390bb75069707980fe5cdeb94010",
        "signature_algorithm": {"name": "SHA256-RSA", "oid": "1.2.840.113549.1.1.11"},
        "spki_subject_fingerprint": "c77933d7cb602adcad550d3bd79edf559062f0db42aa575bbb7f82065ff1b81b",
        "validity": {
            "start": "2022-10-15T00:00:00Z",
            "length": 7862399,
            "end": "2023-01-13T23:59:59Z",
        },
        "validation_level": "OV",
    },
    "uri": "https://id.facebook.org:443/",
    "host_type": "domain",
    "target": {"domain": "id.facebook.org", "type": "domain"},
    "prot7": "http",
    "ptr": ["edge-star-mini-shv-01-gru1.facebook.com"],
    "geo": {
        "continent": "South America",
        "country": "BR",
        "city": "Barueri",
        "tz": "America/Sao_Paulo",
        "location": {"accuracy": 20, "lat": -23.5111, "long": -46.8727},
        "subdivisions": ["SP"],
    },
    "path": "/",
    "protocol": "https",
    "prot4": "tcp",
    "@timestamp": "2023-01-06T05:22:51.401Z",
    "whois": {
        "abuse": "noc@fb.com",
        "related_nets": [],
        "net": {
            "country": "US",
            "address": "1601 Willow Rd.",
            "city": "Menlo Park",
            "created": "2015-05-14",
            "range": "157.240.0.0 - 157.240.255.255",
            "description": "Facebook, Inc.",
            "handle": "NET-157-240-0-0-1",
            "organization": "Facebook, Inc. (THEFA-3)",
            "start_ip": "157.240.0.0",
            "name": "THEFA-3",
            "cidr": ["157.240.0.0/16"],
            "net_size": 65535,
            "state": "CA",
            "postal_code": "94025",
            "end_ip": "157.240.255.255",
            "updated": "2021-12-14",
            "contacts": {"emails": ["noc@fb.com"], "phones": ["+1-650-543-4800"]},
        },
        "asn": {
            "country": "US",
            "registry": "arin",
            "number": ["32934"],
            "name": "FACEBOOK",
            "cidr": "157.240.0.0/17",
            "updated": "2015-05-14",
        },
    },
    "port": 443,
    "domain": [
        "ns1.facebook.co.za",
        "viruses.thefacebook.at",
        "www.dreamscancometruefarms.com",
        "mongo.facebook.com.br",
        "exchange.facebook.com.br",
        "vpn.on.fb.me",
        "antivirus-free.fquestions.com",
        "www.freundes-o.de",
        "postmaster.facebook.com",
        "yuniskanbur.facebook.de",
        "server1.on.fb.me",
        "edge-star-mini-shv-01-gru1.facebook.com",
        "facebook.com",
        "m.fb.me",
        "connect.facebook.it",
        "wap.facebook.com.br",
        "go.facebook.com.br",
        "kosuncovered.thefacebook.at",
        "hubertperron.facebook.fr",
        "id.facebook.org",
    ],
    "host": "id.facebook.org",
    "iteration": "116",
    "http": {
        "headers": {
            "date": ["Fri, 06 Jan 2023 05:20:18 GMT"],
            "content_type": ['text/html; charset="utf-8"'],
            "location": ["https://www.facebook.com/"],
            "connection": ["keep-alive"],
            "alt_svc": ['h3=":443"; ma=86400'],
            "x_fb_debug": [
                "RFWHzJvmFz2VmGnEMEGuUrp++5KjvUp54QMRH/LASEF9AsrEWDXjcn5BhwcElETITZI9y8LYi9ogk41tppPD5w=="
            ],
            "content_length": ["0"],
        },
        "status_code": 302,
        "http_version": {"major": 1, "minor": 1, "name": "HTTP/1.1"},
        "status_line": "302 Found",
    },
    "scan_date": "2023-01-03",
}

```

### datatype="ip-whois"

Corresponds to the results that can be obtained in [Netlas IP Whois Search](https://app.netlas.io/whois_ip/).

```
{
    "last_updated": "2023-09-29T06:58:14.041Z",
    "isp": "Scaleway",
    "ip": "51.159.153.170",
    "ntp": {
        "time_response": {
            "reference_timestamp": {"seconds": 3904958862, "fraction": 2043133245},
            "root_delay": {"seconds": 0, "fraction": 1426},
            "reference_id": "CsUDEA==",
            "root_dispersion": {"seconds": 0, "fraction": 6123},
            "precision": -24,
            "leap_indicator": 0,
            "receive_timestamp": {"seconds": 3904959379, "fraction": 929677788},
            "poll": 3,
            "version": 3,
            "stratum": 5,
            "mode": 4,
            "origin_timestamp": {"seconds": 0, "fraction": 0},
            "transmit_timestamp": {"seconds": 3904959379, "fraction": 929912735},
        },
        "banner": "Version: 3\nTime:\nwall: 216457477\next: 63831567379\nTimeResponse:\nVersion: 3\nMode: 4\nStratum: 5\nPoll: 3\nPrecision: -24\nRootDelay:\nFraction: 1426\nRootDispersion:\nFraction: 6123\nReferenceID: [10, 197, 3, 16]\nReferenceTimestamp:\nSeconds: 3904958862\nFraction: 2043133245\nOriginTimestamp:\nReceiveTimestamp:\nSeconds: 3904959379\nFraction: 929677788\nTransmitTimestamp:\nSeconds: 3904959379\nFraction: 929912735\n",
        "time": "2023-09-29T06:56:19.216457477Z",
        "version": 3,
    },
    "uri": "ntp://51.159.153.170:123",
    "host_type": "ip",
    "prot7": "ntp",
    "target": {"ip": "51.159.153.170", "type": "ip"},
    "ptr": ["170-153-159-51.instances.scw.cloud"],
    "geo": {
        "continent": "Europe",
        "country": "FR",
        "city": "Paris",
        "tz": "Europe/Paris",
        "location": {"accuracy": 1000, "lat": 48.8323, "long": 2.4075},
        "postal": "75001",
        "subdivisions": ["IDF", "75"],
    },
    "protocol": "ntp",
    "prot4": "udp",
    "@timestamp": "2023-09-29T06:58:14.041Z",
    "whois": {
        "abuse": "abuse@online.net",
        "related_nets": [
            {
                "created": "2018-03-28T15:59:36Z",
                "start_ip": "51.158.0.0",
                "description": "SCALEWAY\nParis, France",
                "range": "51.158.0.0 - 51.159.255.255",
                "net_size": 131071,
                "cidr": ["51.158.0.0/15"],
                "updated": "2022-05-03T10:05:58Z",
                "end_ip": "51.159.255.255",
            }
        ],
        "net": {
            "country": "FR",
            "address": "8 rue de la ville l'eveque 75008 PARIS",
            "created": "2018-02-09T11:38:35Z",
            "range": "51.159.0.0 - 51.159.255.255",
            "handle": "MM42047-RIPE",
            "organization": "Scaleway",
            "start_ip": "51.159.0.0",
            "name": "ONLINENET_DEDICATED_SERVERS",
            "net_size": 65535,
            "cidr": ["51.159.0.0/16"],
            "updated": "2018-02-28T16:21:55Z",
            "end_ip": "51.159.255.255",
            "contacts": {"persons": ["Mickael Marchand"], "phones": ["+33173502000"]},
        },
        "asn": {
            "number": ["12876"],
            "country": "FR",
            "registry": "ripencc",
            "name": "Online SAS",
            "cidr": "51.158.0.0/15",
            "updated": "1993-09-01",
        },
    },
    "port": 123,
    "host": "51.159.153.170",
    "iteration": "8",
    "scan_date": "2023-09-22",
}


```

### datatype="cert"

Corresponds to the results that can be obtained in [Netlas Certificates Search](https://app.netlas.io/certs/).

```
{
    "last_updated": "2021-07-24T23:07:33.045Z",
    "@timestamp": "2021-07-24T23:07:33.045Z",
    "certificate": {
        "issuer_dn": "CN=Let's Encrypt Authority X3, O=Let's Encrypt, C=US",
        "fingerprint_md5": "b1a639dfc20b296dbbfa4d038a25d613",
        "chain": [
            {
                "issuer_dn": "CN=DST Root CA X3, O=Digital Signature Trust Co.",
                "fingerprint_md5": "b15409274f54ad8f023d3b85a5ecec5d",
                "redacted": False,
                "signature": {
                    "valid": False,
                    "signature_algorithm": {
                        "name": "SHA256-RSA",
                        "oid": "1.2.840.113549.1.1.11",
                    },
                    "self_signed": False,
                    "value": "3TPXEfNjWDjdGBX7CVW+dla5cEilaUcne8IkCJLxWh9KEik3JHRRHGJouM2VcGfl96S8TihRzZvoroed6ti6WqEBmtzw3Wodatg+VyOeph4EYpr/1wXKtx8/wApIvJSwtmVi4MFU5aMqrSDE6ea73Mj2tcMyo5jMd6jmeWUHK8so/joWUoHOUgwuX4Po1QYz+3dszkDqMp4fklxBwXRsW10KXzPMTZ+sOPAveyxindmjkW8lGy+QsRlGPfZ+G6Z6h7mjem0Y+iWlkYcV4PIWL1iwBi8saCbGS5jN2p8M+X+Q7UNKEkROb3N6KOqkqm57TH2H3eDJAkSnh6/DNFu0Qg==",
                },
                "subject": {
                    "country": ["US"],
                    "organization": ["Let's Encrypt"],
                    "common_name": ["Let's Encrypt Authority X3"],
                },
                "serial_number": "13298795840390663119752826058995181320",
                "version": 3,
                "issuer": {
                    "organization": ["Digital Signature Trust Co."],
                    "common_name": ["DST Root CA X3"],
                },
                "fingerprint_sha256": "25847d668eb4f04fdd40b12b6b0740c567da7d024308eb6c2c96fe41d9de218d",
                "tbs_noct_fingerprint": "3e1a1a0f6c53f3e97a492d57084b5b9807059ee057ab1505876fd83fda3db838",
                "tbs_fingerprint": "3e1a1a0f6c53f3e97a492d57084b5b9807059ee057ab1505876fd83fda3db838",
                "extensions": {
                    "crl_distribution_points": [
                        "http://crl.identrust.com/DSTROOTCAX3CRL.crl"
                    ],
                    "subject_key_id": "a84a6a63047dddbae6d139b7a64565eff3a8eca1",
                    "certificate_policies": [
                        {"id": "2.23.140.1.2.1"},
                        {
                            "cps": ["http://cps.root-x1.letsencrypt.org"],
                            "id": "1.3.6.1.4.1.44947.1.1.1",
                        },
                    ],
                    "key_usage": {
                        "digital_signature": True,
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 97,
                    },
                    "authority_key_id": "c4a7b1a47b2c71fadbe14b9075ffc41560858910",
                    "authority_info_access": {
                        "issuer_urls": [
                            "http://apps.identrust.com/roots/dstrootcax3.p7c"
                        ],
                        "ocsp_urls": ["http://isrg.trustid.ocsp.identrust.com"],
                    },
                    "basic_constraints": {"max_path_len": 0, "is_ca": True},
                },
                "subject_dn": "CN=Let's Encrypt Authority X3, O=Let's Encrypt, C=US",
                "fingerprint_sha1": "e6a3b45b062d509b3382282d196efe97d5956ccb",
                "signature_algorithm": {
                    "name": "SHA256-RSA",
                    "oid": "1.2.840.113549.1.1.11",
                },
                "spki_subject_fingerprint": "78d2913356ad04f8f362019df6cb4f4f8b003be0d2aa0d1cb37d2fd326b09c9e",
                "validity": {
                    "length": 157766400,
                    "start": "2016-03-17T16:40:46Z",
                    "end": "2021-03-17T16:40:46Z",
                },
                "validation_level": "DV",
            },
            {
                "issuer_dn": "CN=DST Root CA X3, O=Digital Signature Trust Co.",
                "fingerprint_md5": "410352dc0ff7501b16f0028eba6f45c5",
                "redacted": False,
                "signature": {
                    "valid": True,
                    "signature_algorithm": {
                        "name": "SHA1-RSA",
                        "oid": "1.2.840.113549.1.1.5",
                    },
                    "self_signed": True,
                    "value": "oxosmxcAXKke7ihmNzq/g8c/S8MJoJUgXePZWUTSPg0+vYpLoHQfzhCCnHQaHX6YGt3LE0uzIETkkenM/H2l22rl/ub94E7dtwA6tXBJr/Ll6wLx0QKLGcuUOl5IxBgeWBlfHgJa8Azxsa2p3FmGi27pkfWGyvq5ZjOqWVvO4qcWc0fLK8yZsDdIz+NWS/XPDwxyMofG8ES7U3JtQ/UmSJpSZ7dYq/5ndnF42w2iVhQTOSQxhaKoAlowR+HdUAe8AgmQAOtkY2CbFryIyRLm0n2Ri/k9Mo1ltOl8sVd26sW2KDm/FWUcyPZ3lmoKjXcL2JELBI4H2ym2Cu6dgjU1EA==",
                },
                "subject": {
                    "organization": ["Digital Signature Trust Co."],
                    "common_name": ["DST Root CA X3"],
                },
                "serial_number": "91299735575339953335919266965803778155",
                "version": 3,
                "issuer": {
                    "organization": ["Digital Signature Trust Co."],
                    "common_name": ["DST Root CA X3"],
                },
                "fingerprint_sha256": "0687260331a72403d909f105e69bcf0d32e1bd2493ffc6d9206d11bcd6770739",
                "tbs_noct_fingerprint": "d0b243776a6c10e4485b34ea3e3b3a063f3089770e04a78c8087b7c49d4f98d6",
                "tbs_fingerprint": "d0b243776a6c10e4485b34ea3e3b3a063f3089770e04a78c8087b7c49d4f98d6",
                "extensions": {
                    "subject_key_id": "c4a7b1a47b2c71fadbe14b9075ffc41560858910",
                    "key_usage": {
                        "certificate_sign": True,
                        "crl_sign": True,
                        "value": 96,
                    },
                    "basic_constraints": {"is_ca": True},
                },
                "subject_dn": "CN=DST Root CA X3, O=Digital Signature Trust Co.",
                "fingerprint_sha1": "dac9024f54d8f6df94935fb1732638ca6ad77c13",
                "signature_algorithm": {
                    "name": "SHA1-RSA",
                    "oid": "1.2.840.113549.1.1.5",
                },
                "spki_subject_fingerprint": "ba285dc8432f62fb8979d84c65660dc04e6219bf716c6dc2e4e49bb2dba68612",
                "validity": {
                    "length": 662662136,
                    "start": "2000-09-30T21:12:19Z",
                    "end": "2021-09-30T14:01:15Z",
                },
                "validation_level": "unknown",
            },
        ],
        "redacted": False,
        "src": "https://ct.googleapis.com/logs/argon2019/",
        "signature": {
            "valid": False,
            "signature_algorithm": {
                "name": "SHA256-RSA",
                "oid": "1.2.840.113549.1.1.11",
            },
            "self_signed": False,
            "value": "IgTWRYQiNa4CEjz9f+MCfnS/n638utteo5ena1WziFXdWasUePWXVM1R5sYIiXUUmt1z/34OSFHpisetgRI683OCEZxZDBiRBsN5lXPs/hMcO14Hs9WhWTrrfUckLHgLOXTiFJ/iCrlKJgUo5QzMFOvwm2iQ9GIMQSS94qRoHBI7U4Upu99ffammpj0Ou4YmBPGXmMngyOx3WtK8eCG7kGEsH01ny8sCUnwtNvlwuKrarw5L0vnnAMzazRzoFDx/vC3R2KewwD8j5eYnF9eI7E7KZSK7Q3eEzboxTO2EZkld40/pdzH+o7B3XOzpJQhglJ3B4iuEZ9Zj9CytNAURCw==",
        },
        "subject": {"common_name": ["l-t.me"]},
        "index": 617433965,
        "serial_number": "298806317781126933132565598755589171656545",
        "version": 3,
        "issuer": {
            "country": ["US"],
            "organization": ["Let's Encrypt"],
            "common_name": ["Let's Encrypt Authority X3"],
        },
        "fingerprint_sha256": "ac3e22f1a55d4db5b66ff6df72ee47cf9c550bc97595f26b6f50a38e38628e2b",
        "tbs_noct_fingerprint": "783f8f2c6844ce3fba97b524e5285b2b4e5f623c18b55d153a0f27087cec67ec",
        "tbs_fingerprint": "9eb431ee59fcd1ebcaaf574d034236786613782891006ac20dac22cb87bae3aa",
        "extensions": {
            "subject_key_id": "53b6643e7203a5e5ffd40b9e9d0a049c3ccab86d",
            "certificate_policies": [
                {"id": "2.23.140.1.2.1"},
                {
                    "cps": ["http://cps.letsencrypt.org"],
                    "id": "1.3.6.1.4.1.44947.1.1.1",
                },
            ],
            "key_usage": {
                "digital_signature": True,
                "key_encipherment": True,
                "value": 5,
            },
            "authority_key_id": "a84a6a63047dddbae6d139b7a64565eff3a8eca1",
            "subject_alt_name": {"dns_names": ["l-t.me"]},
            "signed_certificate_timestamps": [
                {
                    "log_id": "b1N2rDHwMRnYmQCkURX/dxUcEdkCwQApBo2yCJo32RM=",
                    "signature": "BAMARjBEAiBkCDpebkU6+Grogm0B/IG0aEZhaCcfBIiuiofxTyggbgIgJN0bFWWIWyBYDReAlT8x3qKXu1Kh569eCe/YRTUDUbQ=",
                    "version": 0,
                    "timestamp": 1563184252,
                },
                {
                    "log_id": "Y/Lbzeg7zCzPC3KEJ1drM6SNYXePvXWmOLHHaFRL2I0=",
                    "signature": "BAMASDBGAiEArAXCIYXcs3ZhPtge9wVdP2lbGJkCBmoo3wMQkaLmcp0CIQDZHZEuyfO9wy/knwfGaIxVEu/+2+DZS7Irzdx5z8ehoA==",
                    "version": 0,
                    "timestamp": 1563184252,
                },
            ],
            "authority_info_access": {
                "issuer_urls": ["http://cert.int-x3.letsencrypt.org/"],
                "ocsp_urls": ["http://ocsp.int-x3.letsencrypt.org"],
            },
            "basic_constraints": {"is_ca": False},
            "extended_key_usage": {"client_auth": True, "server_auth": True},
        },
        "subject_dn": "CN=l-t.me",
        "names": ["l-t.me"],
        "fingerprint_sha1": "8dd1c6bb83834846c3518a50bd2de5425b679647",
        "signature_algorithm": {"name": "SHA256-RSA", "oid": "1.2.840.113549.1.1.11"},
        "spki_subject_fingerprint": "8c98ec718b8ec4a008524edee0ba9e90e32ef6da97f2eab732004ae0f70de202",
        "validity": {
            "length": 7776000,
            "start": "2019-07-15T08:50:52Z",
            "end": "2019-10-13T08:50:52Z",
        },
        "validation_level": "DV",
    },
}

```










## Netlas CLI Tools

![Netlas cli tools](images/netlas_cli_tools.png)

You can also use the Netlas Python Library directly from the command line. For example:


```
netlas search "http.title:johnsmith" -f json >results.json
```


This simple command searches for all servers that have the word johnsmith in their header, returns the results in JSON format, and stores the results in the resutls.json file.


All other features of the Netlas API can be used in the same way. You can learn more about this from the help (-h command) and examples in the Netlas Cookbook (what you are reading now).


```
Usage: netlas [OPTIONS] COMMAND [ARGS]...

Options:
  -h, --help  Show this message and exit.

Commands:
  count           Calculate count of query results.
  download        Download data.
  host            Host (ip or domain) information.
  indices         Get available data indices.
  profile         Get user profile data.
  savekey         Save API key to the local system.
  search (query)  Search query.
  stat            Get statistics for query.
```


Before running different Netlas CLI Tools commands, save the API key in the settings:


```
netlas savekey YOUR_API_KEY
```


We also have a Github repository with a couple of examples of automating various tasks using bash script and Netlas CLI tools:


[Netlas Scripts](https://github.com/netlas-io/netlas-scripts)


## Search vs Download vs Host methods


The Netlas API has many methods, but the most commonly used methods are search and download. They are very similar to each other, but still have some differences.


The search method loads one page of results (20 items) at a time and allows a maximum of 200 pages to be loaded (20*200=4000 items). The download method downloads all results (but requires much more resources to execute).


There is also a host method that simply returns the most basic information about a particular domain or IP (datatype (like other methods) does not need to be specified):


```
netlas host "51.159.153.170"
```



## Additional request parameters


The Netlas API allows you to flexibly adjust the data returned by requests with additional parameters. For example:

* indices - id that corresponds to a specific indexing date. To find out the id for a specific date, open app.netlas.io, click on the calendar to the right of the search query entry bar, select the date you are interested in and see how the indices parameter in the URL in the browser address bar changes.
* start - result page number (default 0)
* fields - names of fields to be included in the results (all fields by default). It will be useful for speeding up and optimizing code with a large number of requests.


A full list of parameters for the different methods and endpoints can be found here:

[Netlas API Documentation](https://netlas-api.readthedocs.io/en/latest/API_endpoints.html#responses)





## Make requests with Python (without Netlas Python Library)


You may find it easier in some cases not to use the Netlas Python Library, but to use the standard Python request package, which is familiar to many developers:

Enter in the command line:


```
python scripts/python_example.py
```


Source code of python_example.py:

```python
import requests

response = requests.get("https://app.netlas.io/api/domains/?q=ivanov.com&source_type=include&start=0&fields=*",{'X-API-Key': 'YOUR API KEY'})

print(response.json())

```


But Netlas Python Library is still preferable as it is designed to deal with different problems with query processing (errors, long waits, etc.).



## Examples for other programming languages


While we recommend using our Python Library to automate Netlas search, it's worth noting that the Netlas API can be built into most applications with a wide variety of technology stacks. The main thing is that it should be able to make **REST requests** and **parse JSON** data.


Here are some examples in different popular programming languages.


### NodeJS 

![Node JS Netlas](images/netlas_nodejs.png)


Enter in the command line:

```
node scripts/node_example.js
```


If you are not using Gitpod, you should have [NodeJS]([https://nodejs.org/en/download) installed on your device.



Source code of nodejs_example.js:


```javascript

fetch('https://app.netlas.io/api/domains/?q=ivanov.com&source_type=include&start=0&fields=*', {
  headers: {
      "X-API-Key": "YOUR_API_KEY",
  },
})
    .then((response) => response.text())
    .then((body) => {
        var jsonArray = JSON.parse(body);
        console.log(jsonArray['items'][0]);
    });

```


### Ruby 

![Ruby Netlas](images/netlas_ruby.png)



Enter in the command line:


```
ruby scripts/ruby_example.rb
```

If you are not using Gitpod, you should have [Ruby](https://www.ruby-lang.org/en/documentation/installation/) installed on your device.



Source code of ruby_example.rb:


```ruby

require 'net/http'
require 'uri'
require 'json'


uri = URI("https://app.netlas.io/api/domains/?q=ivanov.com&source_type=include&start=0&fields=*")
req = Net::HTTP::Get.new(uri)
req['X-API-Key'] = "YOUR_API_KEY"

res = Net::HTTP.start(uri.hostname, uri.port, use_ssl: uri.scheme == 'https') { |http|
  http.request(req)
}

jsonArray = JSON.parse(res.body)

puts jsonArray['items'][0]['data']['domain']

```


### Bash 

![Bash Netlas](images/netlas_bash.png)


Enter in the command line:


```
bash scripts/bash_example.sh
```

Source code of bash_example.sh:


```
curl -X 'GET' \
  'https://app.netlas.io/api/domains/?q=ivanov.com&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[0].data.last_updated

```

Don't forget that [Netlas Schema](https://app.netlas.io/schema/) automatically generates sample bash scripts (with curl command) for each request. 




## JQ Utility

Note that in the example above, the JQ utility was used to extract fields from JSON data. 

It is sometimes referred to as "like sed for JSON data".  It is a surprisingly handy tool for working with any JSON data. Here are some syntax examples.


Print firt item of JSON-array:

```
.items[0] 
```

Print all items of JSON-array:

```
.items[]
```


Print all 'data' subitems of first item of JSON-array:


```
.['items'][0]['data'][]
```


Print all sub-subitems for each item of JSON-array:

```
.items[].data.technical[]
```



You can read more about JQ here (I recommend paying special attention to data filtering):


[JQ utility documentation](https://jqlang.github.io/jq/)




## AI tools for writing code

![You.com](images/you_com.png)


If you encounter any problems when customising the Netlas Cookbook examples, we recommend that you seek help from AI tools for improving and writing code. For example:


[ChatGPT](https://chat.openai.com/)  
[Code Llama](https://huggingface.co/spaces/codellama/codellama-playground)  
[You.com](https://you.com/)  


When working with such services, you just need to describe in words the task you want to solve with the help of code.


## Code checkers
![Python code check](images/python_code_check.png)

When you rework the Netlas Cookbook examples to suit your purposes, you may find that the code will not execute from some errors. Special online tools can help you find and fix them:  

[ExtendsClass Python Tester](https://extendsclass.com/python-tester.html)
[PythonChecker](https://www.pythonchecker.com)
[Snyk](https://snyk.io/code-checker/python/)



If you don't want to copy your code to third-party services, you can check it for errors on your device using the Pylint (static code analyser):

[Pylint Python Package](https://pypi.org/project/pylint/)



# Using Netlas.io for OSINT (Open Source Intelligence)


![OSINT Flowchart](images/osint_flowchart.png)


Netlas.io can help you gather data about a domain or company, as well as find mentions of a person (or anyone) in internet. 

It can also be used to find old versions of web pages (as an analogue of the Wayback Machine).



## Search person's nickname or email in WHOIS contacts


Most often WHOIS data contains only the contact information of the company registering the domains. But sometimes there may be personal contacts of persons of interest. This query will help you find them.  

*This method may require a paid subscription.* [See the pricing](https://app.netlas.io/plans/)

**Search query example**  

![Whois email search example](images/osint_email_search.png)



```
whois.related_nets.contacts.emails:sweetwater
```

[Try in Netlas](https://app.netlas.io/responses/?q=whois.related_nets.contacts.emails%3Asweetwater&page=1&indices=)

**API request example**


Netlas CLI Tools:


```
netlas search "whois.related_nets.contacts.emails:sweetwater*" -f json
```



Curl:

```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=whois.related_nets.contacts.emails%3Asweetwater*&fields=' \
  -H 'accept: application/json' \
  -H 'X-API-Key: aqkd8L4MR93Tkcaz2UXDXrRleV8Vlvbv' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Whois email search example Python](images/osint_email_search_python.png)



Run in command line:


```
python scripts/osint/whois_email_search.py
```


Source code of scripts/osint/whois_email_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `whois.related_nets.contacts.emails:sweetwater`
netlas_query = netlas_connection.query(query="whois.related_nets.contacts.emails:sweetwater*")


# iterate over data and print: URL, Country, Related nets data
for response in netlas_query['items']:
    print (response['data']['uri'])
    print (response['data']['geo']['country'])
    print (response['data']['whois']['related_nets'])

```









## Search person's nickname or email in title and body of web page


Netlas allows you to search for mentions of certain words in headings and in the html code of web pages. You can search for words by exact match, by approximate match (see the fuzzy queries section) and replace characters you are not sure of with asterisks.



**Search query example**  

![Title/body search example](images/osint_title_body_search.png)



```
http.title:sweetwater OR http.body:sweetwater
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3Asweetwater%20OR%20http.body%3Asweetwater&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search "http.title:sweetwater OR http.body:sweetwater" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=whois.related_nets.contacts.emails%3Asweetwater*&fields=' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Whois email search example Python](images/osint_title_body_search_python.png)



Run in command line:


```
python scripts/osint/title_body_search.py
```


Source code of scripts/osint/title_body_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.title:sweetwater OR http.body:sweetwater`
netlas_query = netlas_connection.query(query="http.title:sweetwater OR http.body:sweetwater*")


# iterate over data and print: IP,URL,web page title
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])
    print (response['data']['http']['title'])

```





## Search links to "juicy info files" on subdomains of the company's website

![Juicy info files search](images/juicyinfo_search.png)


Metagoofil has been a popular tool among OSINT practitioners for many years. It searches Google for document files on a company's website (pdf, xlsx, docx etc) and analyses their metadata.

And what is not indexed by Google can be found with Netlas and then downloaded to your computer and analysed with the [MetaDetective](https://github.com/franckferman/MetaDetective) tool.


```
uri:*lidl.* AND http.body:pdf
```


[Try in Netlas](https://app.netlas.io/responses/?q=uri%3A*lidl.*%20AND%20http.body%3A.pdf&page=1&indices=)


You can replace the uri: filter with domain: and host: (I recommend always comparing the results when using these three filters). 


You can also search for a wide variety of file extensions, depending on what you want to find. For example:


```
http.body:xls
http.body:xlsx
http.body:doc
http.body:docx
http.body:ppt
http.body:pptx
http.body:mdb
http.body:csv
http.body:sql
http.body:sqlite
```


**API request example**

Netlas CLI Tools:

```
netlas search "uri:*lidl.* AND http.body:pdf"
```

Curl:

```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=uri%3A*lidl.*%20AND%20http.body%3Apdf&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.domain
 ```

**Code example (Netlas Python Library)**


![Juicy info search](images/juicyinfo_search_python.png)

Run in command line:

python scripts/osint/juicyinfo_search.py

Source code of scripts/osint/juicyinfo_search.py:


```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `uri:*lidl.* AND http.body:pdf`
netlas_query = netlas_connection.query(query='uri:*lidl.* AND http.body:pdf')


# iterate over data and print: uri, body
for response in netlas_query['items']: 
    print (response['data']['uri'])
    print (response['data']['http']['body'])
```

In order to automate links to PDF documents from the web page body you can use the Python [Re](https://docs.python.org/3/library/re.html) package.





## Phone number mentions search


As with nicknames and emails, you can also look for mentions of a phone number in the code of web pages or WHOIS contact information. 

We single out this task as a separate example, because searching for a phone number is complicated by the fact that it can be written in different formats.



**Search query example**  

![Phone number search example](images/osint_phone_number_search.png)



```
http.body:1?234?567?89?99 OR http.body:12345678999 OR http.body:1234?5678?999
```


[Try in Netlas](https://app.netlas.io/responses/?q=http.body%3A1%3F234%3F567%3F89%3F99%20OR%20http.body%3A12345678999%20OR%20http.body%3A1234%3F5678%3F999&page=1&indices=)




When making a request, you should take into account the format of telephone number recording, which is accepted in the country, which owns the phone number you are interested in.


**API request example**


Netlas CLI Tools:


```
netlas search "http.body:1?234?567?89?99 OR http.body:12345678999 OR http.body:1234?5678?999" -f json
```


Don't forget that you can search for phone numbers not only in the body of the page, but also in the WHOIS contact information. This can be done using the filter **whois.related_nets.contacts.phones:**


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.body%3A1%3F234%3F567%3F89%3F99%20OR%20http.body%3A12345678999%20OR%20http.body%3A1234%3F5678%3F999&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' jq .items[].data.uri
```


**Code example (Netlas Python Library)**

![Phone number search example Python](images/osint_phonenumber_search_python.png)



Run in command line:


```
python scripts/osint/phonenumber_search.py
```


Source code of scripts/osint/phonenumber_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:1?234?567?89?99 OR http.body:12345678999 OR http.body:1234?5678?999`
netlas_query = netlas_connection.query(query="http.body:1?234?567?89?99 OR http.body:12345678999 OR http.body:1234?5678?999")


# iterate over data and print: ip, url
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])

```




## Search file mentions (looking for content that may be infringing on copyrights)


Let's imagine that you are a musician and you want to find all the sites where your tracks are posted. You can do this by searching for pages that mention your name and have links to files with the .mp3 extension.

**Search query example**  

![Title/body search example](images/osint_file_mentions.png)



```
(http.title:alla OR http.body:alla) AND http.body:*.mp3

```

[Try in Netlas](https://nt.ls/HEhJj)




**API request example**


Netlas CLI Tools:


```
netlas search "(http.title:alla OR http.body:alla) AND http.body:*.mp3" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=(http.title%3Aalla%20OR%20http.body%3Aalla)%20AND%20http.body%3A*.mp3&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' |  jq .items[].data.http.title
```




**Code example (Netlas Python Library)**

![File mentions search example Python](images/osint_file_mentions_search_python.png)



Run in command line:


```
python scripts/osint/file_mentions_search.py
```


Source code of scripts/osint/file_mentions_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `(http.title:alla OR http.body:alla) AND http.body:*.mp3`
netlas_query = netlas_connection.query(query="(http.title:alla OR http.body:alla) AND http.body:*.mp3")


# iterate over data and print: IP, URL,web page title
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])
    print (response['data']['http']['title'])

```




## Domain WHOIS information gathering


WHOIS is a worldwide public database that stores information about all registered domains in the world. 


**Search query example**  

![Title/body search example](images/osint_whois.png)

Use [WHOIS Domain search](https://app.netlas.io/whois_domains/)

```
github.com
```


**API request example**


Netlas CLI Tools:


```
netlas host github.com -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/whois_domains/?q=github.com&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' |  jq .items[].data.technical.street
```




**Code example (Netlas Python Library)**

![WHOIS example Python](images/osint_whois_search_python.png)



Run in command line:


```
python scripts/osint/whois_search.py
```


Source code of scripts/osint/whois_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from whois for google.com domain
netlas_query = netlas_connection.query(query="google.com",datatype="whois-domain")


# iterate over data and print: owner name
for response in netlas_query['items']:
    print (response['data']['technical']['name'])  


```



## Search location in \<address\> tag

\<address\> tag is located inside the \<head\> tag of a web page and may contain physical addresses. With a search using this tag, you can find sites associated with a particular street, and sometimes even a particular building.

**Search query example**  

![Author meta search](images/osint_contacts_search.png)



```
http.contacts.address:kirby
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.contacts.address%3Akirby&page=1&indices=)




You can also use http.contacts.email: for email search.


**API request example**


Netlas CLI Tools:


```
netlas search "http.contacts.address:kirby" -f json
```


Curl:


```

curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.contacts.address%3Akirby&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.http.contacts

```


**Code example (Netlas Python Library)**

![Contacts address search Python](images/osint_contacts_search_python.png)



Run in command line:


```
python scripts/osint/contacts_search.py
```


Source code of scripts/osint/contacts_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.contacts.address:kirby`
netlas_query = netlas_connection.query(query="http.contacts.address:kirby")


# iterate over data and print: URL, Contacts
for response in netlas_query['items']:
    print (response['data']['uri'])
    print (response['data']['http']['contacts'])

```



##  Search author name in meta tags

\<meta\> tags are located inside the \<head\> tag of a web page and contain the most important keywords, description, miscellaneous service information and the author's name. 

Searching for nickname and name/surname by meta tags (http.meta) allows you to find sites associated with a particular person faster than searching the entire html code (http.body).


**Search query example**  

![Author meta search](images/osint_author_search.png)



```
http.meta:nazar
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.meta%3Anazar&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search "http.meta:nazar" -f json
```


Curl:


```

curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.meta%3Anazar&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.http.meta

```


**Code example (Netlas Python Library)**

![Author meta search Python](images/osint_author_meta_search_python.png)



Run in command line:


```
python scripts/osint/author_meta_search.py
```


Source code of scripts/osint/author_meta_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.meta:nazar`
netlas_query = netlas_connection.query(query="http.meta:nazar")


# iterate over data and print: ip, url
for response in netlas_query['items']:
    print (response['data']['uri'])
    print (response['data']['http']['title'])
    print (response['data']['http']['meta'])

```



## What other interesting things can be found in the meta tags of html documents?

In addition to the author's name, meta tags can contain a variety of information: encoding, language, permission to index the page by search engine robots, text for link cards in social networks, OpenGraph metadata, and much more. Here are some more examples of meta tags that may contain useful information for investigations:


*  <meta name="description"> - description of web page content.
*  <meta name="keywords">  - keywords that describe the content of the web page.
*  <meta name="generator">  - name of the tool that was used to generate the page content (useful for searching CMS and hosting platforms)
*  <meta name="copyright">  - the name of the person or company who owns the copyright to the content of the web page.



## Search by FTP server's banners text


Another important step in finding information about a person or company is to look for its mention in the text of FTP server banners. It is possible that the IP address of the found servers will be the key to finding other sites related to the person or company you are interested in. And in case of very strong luck to find something interesting in the files posted there (if the FTP server is open).

**Search query example**  


![Search CVE by tag name](images/ftp_banner_search.png)


```
ftp.banner:"Collado" 
```


If you need to search for FTP servers by some other parameter (such as city or IP address range), then use the prot7:ftp filter.



[Try in Netlas](https://app.netlas.io/responses/?q=ftp.banner%3A%22Collado%22%20&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search 'ftp.banner:"Collado"' -f json
```

Note that when double quotes are used in queries, the query itself is written inside single quotes.

Curl:


```
curl -X 'GET' \
    'https://app.netlas.io/api/responses/?q=ftp.banner%3A%22Collado%22&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Favicon hash search Python](images/ftp_banner_search_python.png)



Run in command line:


```
python scripts/osint/ftp_banner_search.py
```


Source code of scripts/osint/ftp_banner_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `ftp.banner:"Collado"`
netlas_query = netlas_connection.query(query='ftp.banner:"Collado"')


# iterate over data and print: IP, URL, ftp banner text
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])
    print (response['data']['ftp']['banner'])


```

## Search for contact information in SSL certificates
![Certificates search](images/certificates_search.png)

An SSL Certificate is a digital certificate that authenticates a website and allows the use of an encrypted connection. It may contain information about it owner: name of the contact person, name of the organisation, country and sometimes even the address and postcode. You can search this information using the following filters (and many others):


```
certificate.issuer.email_address:
certificate.issuer.given_name:
certificate.issuer.organization:
certificate.issuer.postal_code:
certificate.issuer.street_address:
certificate.issuer.surname:

```

Let's try to find IP addresses that have a certain word in the street address in their certificate:

```
certificate.issuer.street_address:*mcgill*
```

[Try in Netlas](https://app.netlas.io/responses/?q=certificate.issuer.street_address%3A*mcgill*&page=1&indices=)


**API request example**


Netlas CLI Tools:


```
netlas search "certificate.issuer.street_address:*mcgill*" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=certificate.issuer.street_address%3A*mcgill*&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' jq .items[].data.uri
```

**Code example (Netlas Python Library)**

![Certificates search Python](images/certificates_search_python.png)



Run in command line:


```
python scripts/osint/certificates_search.py
```


Source code of scripts/osint/certificates_search.py:

```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `certificate.issuer.street_address:*mcgill*`
netlas_query = netlas_connection.query(query="certificate.issuer.street_address:*mcgill*")


print (type(netlas_query))

# iterate over data and print: ip, url, cetificate issuer 
for response in netlas_query['items']:
    print (response['data']['uri'])
    print (response['data']['certificate']['issuer'])  

```




## Using Netlas as an alternative to the WayBack Machine


Archive.org has been used by OSINT specialists to search old versions of websites and social media profiles pages to find now deleted contact and other information.

But, unfortunately, archive.org does not save copies of all sites and does not do it very often (for some sites only a couple of times a year or less).

But Netlas is saving old versions of sites from 2021 too!


Following filters are most often used to search for sites:

```
http.title:"github.com"
domain:github.com
host:github.com

```

![Select scan](images/select_scan.png)


If you click on the outermost icon on the right next to the field for entering search queries, you will see a menu for selecting a scan date. You can use it to filter the html codes of sites saved on a specific date.

![Copy response body](images/response_body_copy.png)

To see how the site looks, copy the contents of the "body" field (response tab) into any text editor and delete the \t\r\n characters from the html code.

![HTML viewer](images/html_viewer.png)

After that, copy the code into one of the online html promoters, such as [Code beautify](https://codebeautify.org/htmlviewer). Or just save the file in html format and then open it in browser.

## 9 ways to search related websites
![Search related websites](images/search_related_websites.png)


When gathering information about a person or company, it can be important to find as many sites as possible that can be related to them in some way. There are at least 5 ways to do this with Netlas.


1. ID for various services (analytics, advertising systems, applications for integration with social networks and publishing systems). Their overlap may indicate that one person or team was involved. Few examples:


Google Analytics:

```
http.body:UA-23870775
```

Google Tag Manager:

```
http.body:GTM-WCBNVW
```

AddThis:

```
http.body:AT-ra-500bcd681b192302
```

Facebook Pixel:

```
http.body:FB-XXXXXXXXXXXXXXXX
```

Google+:

```
http.body:GP-1XXXXXXXXXXXXXXXXXXXXX
```
       
Amazon Publisher Servies:

```
http.body:APS-XXXX
```

Yes, it's all found in the code on some sites.
 
And a host of other indetifiers that can most often be found at the top of the html code (but sometimes all over the code).

[Try in Netlas](https://app.netlas.io/responses/?q=http.body%3AUA-23870775&page=1&indices=)


2. ID of affiliate programmes (also use http.body for search it). You can find them in affiliate links that a person publishes on other sites or in social networks. These can be the following URL parameters (and their like):

```
aff_fcid=
user_id=
partner_id=
ref_id=
```

3. Search by organization name in Domain Whois Netlas search

![Search organization in WHOIS](images/search_organization_whois.png)

```
"GitHub, Inc."
```

[Try in Netlas](https://app.netlas.io/whois_domains/?q=%22GitHub%2C%20Inc.%22&page=1&indices=)

4. Search by mail servers in DNS Netlas search

![Search mail servers in DNS](images/search_mail_servers_dns.png)


```
mx:*.parklogic.com
```

[Try in Netlas](https://app.netlas.io/domains/?q=mx%3A*.parklogic.com&page=1&indices=)

5. Search by name servers in DNS Netlas search

![Search name servers in DNS](images/search_name_servers_dns.png)

```
ns:ns?.parklogic.com
```

[Try in Netlas](https://app.netlas.io/domains/?q=mx%3A*.parklogic.com&page=1&indices=)

6. Files (primarily user logos and avatars) mentions search [->](https://github.com/netlas-io/netlas-cookbook#search-file-mentions-looking-for-content-that-may-be-infringing-on-copyrights)


7. Subdomain search [->](https://github.com/netlas-io/netlas-cookbook#search-subdomains)

8. Whois contacts search (in Netlas response search) [->](https://github.com/netlas-io/netlas-cookbook#search-persons-nickname-or-email-in-whois-contacts)

9. Favicon search [->](https://github.com/netlas-io/netlas-cookbook#favicon-search)







# Scraping (extract data from web page body)

Netlas API is a great tool for collecting contact and other website data. First, it allows you to do it quickly. Second, it does not require the use of proxy. Third, it allows you to collect data from sites that are currently unavailable.

However, there are some disadvantages: Netlas scans only the main pages of sites (not all of them) and some rare sites are not included in its database due to protection.  But it can still be of great use.


There are three main approaches to scraping: collecting information from html tags and CSS selectors, extracting data using regular expressions, and AI scraping. Let's take a closer look at the first two. 


## Beatifulsoup package


[Beatifulsoup](https://pypi.org/project/beautifulsoup4/) - is one of the world's most popular Python packages for parsing HTML code and XML files. Let's try using it to extract page titles (from \<h1> tags, NOT <title> tages).

First, install package:

```
pip install beautifulsoup4
```


And Run scripts/osint/scraping_beatifulsoup.py:


```
python scripts/osint/scraping_beatifulsoup.py
```

![Beatiful soup scraping](images/scraping_beatifulsoup.png)



Source code of scripts/osint/scraping_beatifulsoup.py:

```python
import netlas
from bs4 import BeautifulSoup

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:shop`
netlas_query = netlas_connection.query(query="http.body:shop")


# iterate over data and print: URL, h1 tags from body
for response in netlas_query['items']:
    print (response['data']['uri'])
    soup = BeautifulSoup(response['data']['http']['body'], "html.parser")
    try:
        print(soup.find("h1").get_text())
    except Exception:
        print("no h1 tags")
pass
```


You can extract data from other elements of web pages in a similar way:

```
soup.find("h3").get_text()
soup.find("id='loginform'").get_text()
soup.find("class='forms'").get_text()
soup.find("href='https://example.com'").get_text()
```

If you want to find all elements of a certain type use the find_all() method.


## Re package


[Re](https://docs.python.org/3/library/re.html) is a pre-installed Python package for searching and retrieving data using regular expressions. It is useful for extracting contact information from web pages and many other tasks. Let's look at an example of how it works.


Run scripts/osint/scraping_re.py:

```
python scripts/osint/scraping_re.py
```

![Re scraping](images/scraping_re.png)

Source code of scripts/osint/scraping_re.py:

```python
import netlas
import re

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:shop`
netlas_query = netlas_connection.query(query="http.body:shop")


# iterate over data and print: URL, emails from body
for response in netlas_query['items']:
    print (response['data']['uri'])
    emails = re.findall("[a-zA-Z0-9-_.]+@[a-zA-Z0-9-_.]+", response['data']['http']['body'])
    try:
        print(emails)
    except Exception:
        print("no emails")
pass
```

Similarly, you can extract links, phone numbers, cryptocurrency wallet addresses and more. Ready patterns can be found in regular expression libraries:

[Regex Lib](https://regexlib.com/)
[UI Bakery Regex Library](https://uibakery.io/regex-library)
[Regex 101](https://regex101.com/)




## Other Python packages for scraping


Beaitiful soup and Re packages are just one of the many tools for scraping data from web pages using Python. Here are some more examples of such packages:


* [Scrapy](https://pypi.org/project/Scrapy/) - It is primarily a crawler (a tool for traversing website pages using links found on other pages) and, in addition, it has extensive capabilities for extracting data from web pages.

* [Selenium](https://pypi.org/project/selenium/) - A tool for automating your browser experience. Allows you to extract data from contentthat is generated by JavaScript.

* [Lxml](https://pypi.org/project/lxml/) - tool for scraping and validate XML files. 


* [PDFtoText](https://pypi.org/project/pdftotext/) - tool for extracting text content from PDF files.

* [pyChatGPT](https://pypi.org/project/pyChatGPT/) - unofficial package for interaction with CHATGP (does not require OpenAI API key), which allows analyzing text information with AI.






# Using Netlas.io for Crypto Investigations


Netlas provides a great opportunity for researchers who specialise in cryptocurrency crime. 

Firstly, it can be used to search for references to wallet addresses and transaction numbers. 

Second, it can be used to search for vulnerable mining farms, nodes and other servers associated with crypto infrastructure.


## Search mining farms

![Search mining farms](images/search_mining_farms.png)

Antminer mining farms, which were first released by Bitmain back in 2013, are one of the most popular line of mining farm models in the world. You can find them by the presence of the word "antMiner" in the www_authenticate header.


```
http.headers.www_authenticate:antMiner
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.headers.www_authenticate%3AantMiner&page=1&indices=)


You can also search for other types of mining farms. For examples:


```
http.headers.www_authenticate:XMR-Stak-Miner
```

Experiment by combining different filters, the words "miner/mining" and cryptocurrency names.


**API request example**

Netlas CLI Tools:

```
netlas search "http.headers.www_authenticate:antMiner"
```


Curl:

```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.headers.www_authenticate%3AantMiner&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.uri
 ```

**Code example (Netlas Python Library)**


![Maining farms search Python](images/maining_farms_search_python.png)

Run in command line:

```
python scripts/crypto/mining_farms_search.py
```

Source code of scripts/crypto/mining_farms_search.py:

```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.headers.www_authenticate:antMiner`
netlas_query = netlas_connection.query(query='http.headers.www_authenticate:antMiner')


# iterate over data and print: uri, http headers
for response in netlas_query['items']: 
    print (response['data']['uri'])
    print (response['data']['http']['headers'])
```




## Search for websites infected with cryptominers

![Search website injected with miners](images/search_sites_injected_with_miners.png)


Coinhive, a service that allows websites (mostly hacked) to use their visitor's computers to mine cryptocurrencies, is shutting down in 2019. But nevertheless, links to it are still embedded in many sites around the world. Let's try to find them:


```
http.body:coinhive.min.js domain:*
```


Note that we use the domain:* filter to find sites specifically, not all devices.


Similarly, you can search for sites infected with other cryptominers (as well as other malicious code that executes on the user's side).


**API request example**

Netlas CLI Tools:

```
netlas search "http.body:coinhive.min.js domain:*"
```


Curl:

```
curl -X 'GET' \
   'https://app.netlas.io/api/responses/?q=http.body%3Acoinhive.min.js%20domain%3A*&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.uri
 ```

**Code example (Netlas Python Library)**


![Maining farms search Python](images/search_sites_injected_with_miners_python.png)

Run in command line:

```
python scripts/crypto/search_sites_injected_with_miners.py
```

Source code of scripts/crypto/search_sites_injected_with_miners.py:


```
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:coinhive.min.js domain:*`
netlas_query = netlas_connection.query(query='http.body:coinhive.min.js domain:*')


# iterate over data and print: uri
for response in netlas_query['items']: 
    print (response['data']['uri'])
```





## Search vulnerable Bitcoin nodes
![Search bitcoin nodes](images/search_bitcoin_nodes.png)


Bitcoin nodes use port 8333 for TCP connection. Therefore, it is easy to find them using the "port:" search filter.


```
port:8333 cve:*
```

Note that we use the "cve:*" filter to look for servers with vulnerabilities.


**API request example**

Netlas CLI Tools:

```
netlas search "port:8333 cve:*"
```


Curl:

```
curl -X 'GET' \
    'https://app.netlas.io/api/responses/?q=port%3A8333%20cve%3A*&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.uri
 ```

**Code example (Netlas Python Library)**


![Search bitcoin nodes Python](images/search_bitcoin_nodes_python.png)

Run in command line:

```
python scripts/crypto/search_bitcoin_nodes.py
```

Source code of scripts/crypto/search_bitcoin_nodes.py:


```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `port:8333 cve:*`
netlas_query = netlas_connection.query(query='port:8333 cve:*')


# iterate over data and print: uri, CVE name and description
for response in netlas_query['items']: 
    print (response['data']['uri'])
    print (response['data']['cve'][0]['name'])
    print (response['data']['cve'][0]['description'])
```


# Using Neltas for Pentest


Netlas.io allows you to search for sites with many different types of vulnerabilities. This can be done by vulnerability number (CVE-...), the name of the software installed on the server, certain words in page headers, and other parameters.


You can track the most recently published CVEs (Common Vulnerabilities and Exposures) on these sites:

* [CVE Details](https://www.cvedetails.com/)
* [VulDB](https://vuldb.com/)
* [OpenCVE](https://www.opencve.io/cve)


We also regularly post most relevant queries to search vulnerable devices and software on our [Twitter](https://twitter.com/Netlas_io) and [Telegram](https://t.me/netlas) feeds, as well as [Netlas Dorks](https://github.com/netlas-io/netlas-dorks) Github repository.


You can also check out our two articles about Attack Surface:
- [Complete Guide on Attack Surface Discovery](https://netlas.io/blog/attack_surface_discovery_guide/).
- [Best Attack Surface Visualization Tools](https://netlas.io/blog/best_attack_surface_visualization_tools/).


In this section, we will simply cover the general principles of searching for sites and servers with vulnerabilities.



## Search subdomains


By using asterisks in search queries, you can find all subdomains of different levels (whose name ends with the name of a particular first-level domain (.com) or second-level domain (google.com).

**Search query example**  

![Subdomain search example](images/osint_subdomain_search.png)



```
domain:*.github.com OR host:*.github.com
```



[Try in Netlas](https://app.netlas.io/responses/?q=domain%3A*.github.com%20OR%20host%3A*.github.com&page=1&indices=)




**API request example**


Netlas CLI Tools:


```
netlas search "domain:*.github.com OR host:*.github.com" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=domain%3A*.github.com%20OR%20host%3A*.github.com&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Subdomain search example Python](images/osint_subdomain_search_python.png)



Run in command line:


```
python scripts/pentest/subdomain_search.py
```


Source code of scripts/pentest/subdomain_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `domain:*.github.com OR host:*.github.com`
netlas_query = netlas_connection.query(query="domain:*.github.com OR host:*.github.com")


# iterate over data and print: ip, url
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])

```





## Search for sites with specific vulnerabilities




**Search query example**  

![CVE search](images/pentest_cve_search.png)



```
cve.name:CVE-2022-22965
```

[Try in Netlas](https://app.netlas.io/responses/?q=cve.name%3ACVE-2022-22965&page=1&indices=)


**API request example**


Netlas CLI Tools:


```
netlas search "cve.name:CVE-2022-22965" -f json
```


CVE-2022-22965 - Spring MVC or Spring WebFlux application running on JDK 9+ may be vulnerable to remote code execution (RCE) via data binding. [Details](https://nvd.nist.gov/vuln/detail/cve-2022-22965)


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.body%3A1%3F234%3F567%3F89%3F99%20OR%20http.body%3A12345678999%20OR%20http.body%3A1234%3F5678%3F999&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' jq .items[].data.uri
```


**Code example (Netlas Python Library)**

![CVE search example Python](images/pentest_cve_search_python.png)



Run in command line:


```
python scripts/pentest/cve_search.py
```


Source code of scripts/pentest/cve_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `cve.name:CVE-2022-22965`
netlas_query = netlas_connection.query(query="cve.name:CVE-2022-22965")


# iterate over data and print: ip, url
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])

```



## Search for sites with vulnerabilities that contain a certain word in their descriptions


If you don't need to investigate servers with a specific type of vulnerability, but just want to see vulnerable servers in a specific group (such as Oracle WebLogic Server or WordPress sites), you can search for them using keywords and the cve.description: filter. 

To filter out sites that have exploits published for vulnerabilities, use cve.has_exploit:true.


**Search query example**  

![CVE description search](images/pentest_cve_description_search.png)



```
cve.description:weblogic AND cve.has_exploit:true
```

[Try in Netlas](https://app.netlas.io/responses/?q=cve.description%3Aweblogic%20AND%20cve.has_exploit%3Atrue&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search "cve.description:weblogic AND cve.has_exploit:true" -f json
```


Curl:


```

curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=cve.description%3Aweblogic%20AND%20cve.has_exploit%3Atrue&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY | jq .items[].data.uri

```


**Code example (Netlas Python Library)**

![CVE description search Python](images/pentest_cve_description_search_python.png)



Run in command line:


```
python scripts/pentest/cve_description_search.py
```


Source code of scripts/pentest/cve_description_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `cve.description:weblogic AND cve.has_exploit:true`
netlas_query = netlas_connection.query(query="cve.description:weblogic AND cve.has_exploit:true")


# iterate over data and print:  url, first CVE name first CVE description
for response in netlas_query['items']:
    print (response['data']['uri'])
    print (response['data']['cve'][0]['name'])
    print (response['data']['cve'][0]['description'])

```



## Search by server http header


This method allows you to find devices manufactured by a specific company.

**Search query example**  


![Search by server software](images/server_name_search.png)


```
http.headers.server:"yawcam"
```


Search YawCam web cams.


[Try in Netlas](https://app.netlas.io/responses/?q=http.headers.server%3A%22yawcam%22&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search 'http.headers.server:"yawcam"' -f json
```

Note that when double quotes are used in queries, the query itself is written inside single quotes.

Curl:


```
curl -X 'GET' \
     'https://app.netlas.io/api/responses/?q=http.headers.server%3A%22yawcam%22&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Http headers server search Python](images/server_name_search_python.png)



Run in command line:


```
python scripts/pentest/server_name_search.py
```


Source code of scripts/pentest/server_name_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.headers.server:"yawcam"`
netlas_query = netlas_connection.query(query='http.headers.server:"yawcam"')


# iterate over data and print: IP, URL, server name
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['http']['headers']['server'])

```

### Default logins and passwords 


One practical application of searching by software name in server headers is to search for devices from a particular vendor. This may be necessary both when searching for devices with specific vulnerabilities and for devices with standard logins and passwords.


![Default passwords](images/default_passwords.png)


Standard logins and passwords for different device models can be found in special lists. For example:


* [Default Router Login Password For Top Router Models (2023 List)](https://www.softwaretestinghelp.com/default-router-username-and-password-list/)
* [Default Username – Password – IP Address for Security Cameras](https://www.a1securitycameras.com/blog/default-username-passwords-ip-addresses-for-surveillance-cameras/)
* [The Default Passwords of Nearly Every IP Camera](https://www.hackers-arise.com/post/the-default-passwords-of-nearly-every-ip-camera)
* [List of default passwords from Datarecovery](https://datarecovery.com/rd/default-passwords/)


Remember that using standard logins and passwords to log into other people's systems violates ethics rules and may be illegal in your country.



## Search servers with CVEs by favicon hash


One way to find web servers exposed to a particular vulnerability is to search for favicon ico of a particular web server software. 


**Search query example**  


![Search CVE by favicon hash](images/search_favicon_hash.png)


```
http.favicon.hash_sha256:ebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e
```

This query search SecurePoint favicon (CVE-2023-22620).


[Try in Netlas](https://app.netlas.io/responses/?q=http.favicon.hash_sha256%3Aebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search "http.favicon.hash_sha256:ebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e" -f json
```


Curl:


```
curl -X 'GET' \
   'https://app.netlas.io/api/responses/?q=http.favicon.hash_sha256%3Aebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Favicon hash search Python](images/search_favicon_hash_python.png)



Run in command line:


```
python scripts/pentest/favicon_hash_search.py
```


Source code of scripts/pentest/favicon_hash_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.favicon.hash_sha256:ebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e`
netlas_query = netlas_connection.query(query="http.favicon.hash_sha256:ebaaed8ab7c21856f888117edaf342f6bc10335106ed907f95787b69878d9d9e")


# iterate over data and print: IP,URL,web page title
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])
    print (response['data']['http']['title'])

```


## Search servers with CVEs by tag name


To simplify searching across servers running different software, Netlas automatically tags search results with specific tags.


Examples of tags:

* Blogs - medium, wordpress, tumblr
* CDN - google_cloud, cloudflare, keycdn
* CMS - ucoz, joomla, pyrocms
* Ecommerce - opencart, magento, wix


You can search by tags using the "tag.name:" filter. You can also search by tag category using the "tag.category:" filter. A list of all available tags and categories is displayed when you click on the icon to the right of the search query entry box on the Netlas homepage. 

*Note*: Not all tariff plans support the use of tags, be careful.


**Search query example**  


![Search CVE by tag name](images/search_tag_name.png)


```
tag.name:"adobe_coldfusion"
```

This query search Adobe ColdFusion (CVE-2023-26359).


[Try in Netlas](https://app.netlas.io/responses/?q=tag.name%3A%22adobe_coldfusion%22&page=1&indices=)



**API request example**


Netlas CLI Tools:


```
netlas search 'tag.name:"adobe_coldfusion"' -f json
```

Note that when double quotes are used in queries, the query itself is written inside single quotes.

Curl:


```
curl -X 'GET' \
    'https://app.netlas.io/api/responses/?q=tag.name%3A%22adobe_coldfusion%22&source_type=include&start=0&fields=*'  \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' | jq .items[].data.uri
```




**Code example (Netlas Python Library)**

![Favicon hash search Python](images/search_tag_name_python.png)



Run in command line:


```
python scripts/pentest/search_tag_name.py
```


Source code of scripts/pentest/search_tag_name.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `tag.name:"adobe_coldfusion"`
netlas_query = netlas_connection.query(query='tag.name:"adobe_coldfusion"')


# iterate over data and print: IP,URL 
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (response['data']['uri'])
```




## Search vulnerable servers and devices near you (or any other location)

![CVE location search](images/cve_location_search.png)


Do you want to know how many vulnerable sites and devices are around you? Simply search for all IP addresses that have the CVE field populated in a specific geolocation.

```
geo.city:London AND cve:*
```

[Try in Netlas](https://app.netlas.io/responses/?q=geo.city%3ALondon%20AND%20cve%3A*&page=1&indices=)


You can also use other geolocation filters.

```
geo.continent:
geo.country:
geo.location:
geo.location.lat:
geo.location.long:
```


**API request example**

Netlas CLI Tools:

```
geo.city:London AND cve:*
```

Curl:

```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=geo.city%3ALondon%20AND%20cve%3A*&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.domain
 ```

**Code example (Netlas Python Library)**


![Location CVE search Python](images/cve_location_search_python.png)

Run in command line:

python scripts/pentest/cve_location_search.py

Source code of scripts/pentest/cve_location_search.py:


```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `geo.city:London AND cve:*`
netlas_query = netlas_connection.query(query='geo.city:London AND cve:*')


# iterate over data and print: uri, cve name, location
for response in netlas_query['items']: 
    print (response['data']['uri'])
    print (response['data']['cve'][0]['name'])
    print (response['data']['geo']['city'])

```



## Search for login/admin panels
![Admin panels search](images/admin_panels_search.png)


Many sites and servers have login and password web pages that can be used to gain access to full control of the site or server (through the use of default passwords, bruteforce, or vulnerability exploitation).

You can find them by using the **uri:** or/and **http.title** filter:

```
uri:*login.php*
uri:*login.aspx*
uri:*user* http.title:login
uri:*admin* http.title:login
http.title:admin http.title:panel
```

There are so many combinations. To find only panels of vulnerable servers use filter cve:*.


Also, don't forget that you can filter servers by installed software using tags. For example:


```
tag.1c_bitrix:*
tag.Cisco:
tag.amazon_s3:*
tag.drupal:*
tag.wordpress:*
```




## Search for vulnerable database admin panels
![Database admin panels search](images/database_admin_panels_search.png)

Let's try to search vulnerable [phpMyAdmin](https://www.phpmyadmin.net/) admin panel (the one of most popular software for administering MySQL databases):

```
http.title:phpMyAdmin cve:*
```

And here are some examples for other popular database administration tools:


[Adminer](https://www.adminer.org/):

```
http.title:adminer http.title:login cve:*
```

[PostgreSQL](https://www.postgresql.org/)

```
http.title:(phpPgAdmin OR pgadmin) cve:*
```


You can also search for servers that have installed software for different databases by using the tags or special filters:


```
tag.adminer:*
tag.phpMyAdmin:*
tag.elastic:*
mongodb:*
mssql:*
mysql:*
django:*
```

Searching for admin panels for servers found in this way may not be the easiest thing to do, as site administrators often change standard links to more secure ones. 




## Search for sites vulnerable to SQL injection

![SQL Injection search](images/sql_injection_search.png)

SQL injection is a type of vulnerability that allows database queries to be made by manipulating URL parameters (this can be possible due to misconfigurations and poor quality code). 

One of the oldest techniques for finding pages potentially vulnerable to SQL Injection is to search for pages that have enabled error message display in MySQl queries using Google Dorks. 

A similar search can be done in Netlas:

```
http.body:mysql_fetch_array http.body:warning
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.body%3Amysql_fetch_array%20http.body%3Awarning&page=1&indices=)


Few other examples:

```
http.body:mysql_num_rows http.body:warning
http.body:mysql_connect http.body:denied
http.body:mysql_query http.body:warning
http.body:pg_connect http.body:fatal
```


**API request example**


Netlas CLI Tools:


```
netlas search "http.body:mysql_fetch_array http.body:warning" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.body%3Amysql_fetch_array%20http.body%3Awarning&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' jq .items[].data.uri
```

**Code example (Netlas Python Library)**

![SQL Injection search Python](images/sql_injection_search_python.png)



Run in command line:


```
python scripts/pentest/sql_injection_search.py
```


Source code of scripts/pentest/sql_injection_search.py:


```python
import netlas

apikey = "YOUR_API_KEY"
 
# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# search in Netlas "http.body:mysql_fetch_array http.body:warning"
netlas_query = netlas_connection.query(query="http.body:mysql_fetch_array http.body:warning")


# iterate over data and print: uri, web page body
for response in netlas_query['items']:
    print (response['data']['uri'])  
    print (response['data']['http']['body'])    
```

You may also use the following filters to search for vulnerable MySQL servers:

```
mysql.error_code:
mysql.error_id:
mysql.error_message:
```



# IoT search: 9 basic ways

Netlas searches not only websites and servers, but all devices connected to the Internet: smart home appliances, surveillance cameras, printers, routers, traffic lights, medical equipment, and more. 

There are four main ways to find these devices.


## Search by http.title

![Iot Title Search](images/iot_title.png)


The easiest way is to simply search for the vendor's name or device type in the http title of the answer.

Try to search Jeedom home automation devices:

```
http.title:Jeedom
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3AJeedom&page=1&indices=)

Or Avigilon webcams:

```
http.title:"Avigilon"
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.title%3A%22Avigilon%22&page=1&indices=)

There are two disadvantages to this method. The first is the large number of inappropriate results (just websites with relevant words in the title). But when using quotation marks and additional search filters like port:, there are fewer of them.

The second is that a lot of IoT devices don't have any information in the http title by which they can be identified. So, other search filters can be useful too.



## Search by http.body

![Iot Body Search](images/iot_body.png)

Similarly, you can try searching for keywords in the body of the http response. To filter out at least some of the common websites, use the NOT domain:* filter. Let's try to search Reolink cameras:

```
http.body:(clip-status) NOT domain:*
```

The example isn't quite right, so these cameras can be found using tags (more on that below).


## Search by port

![Iot port search](images/iot_port.png)


Different IoT devices use different ports for communication. And by the open port number, you can hypothetically assume that the IP address belongs to a certain type of device (**often the assumption is correct, but there can be inaccuracies and coincidences**).


Try to search Internet radio(port 8000):

```
port:8000 http.title:radio
```

[Try in Netlas](https://app.netlas.io/responses/?q=port%3A8000%20http.title%3Aradio&page=1&indices=)

Or all devices with opened port 7547 (it's used to remotely manage routers via CWMP):


```
port:7547
```

[Try in Netlas](https://app.netlas.io/responses/?q=port%3A7547&page=1&indices=)

## Search by banner
![Iot banner search](images/iot_banner.png)

Let's look for routers that use the Telnet protocol (you could also filter them with port:23):

```
telnet.banner:router
```

[Try in Netlas](https://app.netlas.io/responses/?q=telnet.banner%3Arouter&page=1&indices=)

Or search banners for all protocols:

```
\*.banner:router
```

[Try in Netlas](https://app.netlas.io/responses/?q=%5C*.banner%3Arouter&page=1&indices=)

## Search by favicon
![Iot favicon search](images/iot_favicon.png)

One of the easiest ways to find devices that have certain software installed is to search by favicon. Let's try to find where different Cisco products are used: 

```
http.favicon.hash_sha256:62a8461e328d5bace3780ff738d0b58f6502592c04afa564e0a8a792583a7bfb
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.favicon.hash_sha256%3A62a8461e328d5bace3780ff738d0b58f6502592c04afa564e0a8a792583a7bfb&page=1&indices=)

There are three main ways to search by favicon in Netlas:

1. Click on the icon to the left of the search result.
2. Click on the favicon search button to the right of the search bar and paste the favicon link into the pop-up window.
3. Click on the favicon search button to the right of the search bar and upload the favicon file.


## Search by server headers
![Iot headers search](images/iot_headers.png)

Sometimes it happens that there is no identifying dev information in the http title, but it may be in other headers. For example, in http.server.header:

```
http.headers.server:"i-Catcher Console"
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.headers.server%3A%22i-Catcher%20Console%22&page=1&indices=)

Netlas supports searching across several dozen header types. Try different variants.


## Search by cookies

![Iot cookie search](images/iot_headers_cookie.png)


Search Eco JS Parking lots:

```
http.headers.set_cookie:(regist_carNo=)
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.headers.set_cookie%3Aregist_carNo%3D&page=1&indices=)

## Search by tag
![Iot tag search](images/iot_tag.png)

*This method may require a paid subscription.* [See the pricing](https://app.netlas.io/plans/)

You can also try searching for devices by tags (categories). 

```
tag.category:"IoT"
tag.category:"Web cameras"
```

[Try in Netlas](https://app.netlas.io/responses/?q=tag.category%3A%22Web%20cameras%22&page=1&indices=)

Just remember that tags are assigned automatically and some suitable devices may not be included in the corresponding category.

## Additional search filters


It's can search for IoT devices located in specific geolocations:


```
geo.city:
geo.country:
geo.continent:
geo.location.lat:
geo.location.long:
```

Filter devices by IP address range:


```
ip:[162.245.241.131 TO 162.245.241.133]
```

Or devices with "fresh" vulnerabilities:

```
cve.name:*2023*
```


More examples of queries to search for IoT devices can be found here:

[Netlas Dorks](https://github.com/netlas-io/netlas-dorks)










# Using Netlas.io for Darknet research


One of the main advantages of Netlas is that you can use it to search for things that are not indexed by Google. This is what can be conventionally called DeepWeb. For example, FTP servers or Telnet servers:

```
ftp.banner:*
telnet.banner:*
```


But unfortunately Netlas does not index the Darknet (.onion, .i2p etc) as it only scans global IP addresses. But it can still be used to explore alternative network infrastructure and find links to .onion sites.


## Tor exit nodes search

Tor exit node is the point whrerer web traffic leaves the Tor network and is forwarded to destination. An up-to-date list of IP addresses of active Tor entry nodes is always available on the TorProject website:

[Tor Project's list of exit nodes](https://check.torproject.org/torbulkexitlist?ip=1.1.1.1)


Let's see how you can collect information about all active Tor exit nodes at once using Netlas. This example will be useful for all other tasks for which you need to collect information about a list of domains or IP addresses.


Run scripts/darknet/tor_nodes.py:

```
python scripts/darknet/tor_nodes.py
```

![Tor exit nodes information gathering](images/tor_exit_nodes.png)

Source code of scripts/darknet/tor_nodes.py:

```python

import netlas
import urllib
import time

apikey = 'YOUR_API_KEY'

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# read file with Tor Exit Nodes IPs line by line
response = urllib.request.urlopen('https://check.torproject.org/torbulkexitlist?ip=1.1.1.1')
ip_lines = response.readlines()

# save each line to ip variable
for ip in ip_lines:
     # wait one second
     time.sleep(1)
     # conver byte string to text
     ip=ip.decode("utf-8")
     # retrieve data from responses by query `ip: + tor exit node ip`
     netlas_query = netlas_connection.query(query="ip:"+ip)

    # iterate over data and print: ip, geo data, banner text

     for response in netlas_query['items']:
         print(response['data']['ip'])
         print(response['data']['geo'])
         print(response['data']['ntp']['banner'])
     pass
pass

```

Using time package and sleep method is good only for simple examples. Best solutions is using [rate limit package](https://github.com/netlas-io/netlas-cookbook#error-429---too-frequent-requests).



## Collecting links to .onion sites


As mentioned above, Netlas only scans global domains, so it is not possible to search for .onion domains. But you can search for references to .onion domains in the text of web pages.  Here is an example of a simple python script (with regular expression) that does this:


Run scripts/darknet/onion_links.py:

```
python scripts/darknet/onion_links.py
```

![Onion links collecting](images/onion_links.png)

Source code of scripts/darknet/onion_links.py:


```python
import netlas
import re

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:*.onion AND forum`
netlas_query = netlas_connection.query(query="http.body:(*.onion AND forum)")


# iterate over data and print: URL, .onion link from body
for response in netlas_query['items']:
    print(response['data']['uri'])
    onion_links = re.findall("[a-z-1-9]*\.onion", response['data']['http']['body'])  
    try:
         print(onion_links)
    except:
         print("no onion links")
pass

```

You can collect links for other networks like I2Pin the same way:

```
http.body:*.i2p
```
















# Files, backups and logs directories search

![Directory search](images/directory_search.png)


There are a huge number of sites and servers that leave their file directories open due to a configuration error (and sometimes deliberately). Here are some examples of queries that will help you find them.


Search for any files directories:

```
http.title:Index http.title:of
```

Search for directories with log files:

```
http.title:Index http.title:of http.body:logs
```

Search for directories with database dumps:

```
http.title:Index http.title:of http.body:sql
```

Search for directories with archived backups:

```
http.title:Index http.title:of http.body:backup?zip
```

Search for directories with SSH access info:

```
http.title:Index http.title:of http.body:("ssh_config" OR "ssh_known_hosts" OR "authorized_keys" OR "id_rsa" OR "id_dsa")
```

Search for directories with files with other authorisation information:

```
http.title:Index http.title:of http.body:("pass" OR "logins" OR "config" OR "password")
```

Search for directories with files downloaded by users:

```
http.title:index http.title:of http.body:downloads
```

Search for directories with Docker configuration files:

```
http.title:index http.title:of http.body:docker-compose
```


You can think of hundreds of other such requests. Experiment with different file names and extensions.





# Using Netlas.io for Digital Forensics and Incident Response



This section is very difficult to separate from the Netlas for OSINT section, as the queries listed therein will also be useful to those involved in digital forensics.

In this section, we describe more "technical" queries that can help, for example, gather information about the technical infrastructure of networks or investigate phishing attacks.


## SMTP servers information gathering

SMTP (Simple Mail Transfer Protocol) is a communication protocol that enables to send and receive emails. In most email clients, when viewing emails, the "Show Original" function is available, which allows you to view the address of the SMTP server from which the email was sent.


Netlas allows you to get information about an SMTP server as well as about any other IP or domain, as well as to search the text of SMPT banners, which allows you to find servers associated with a particular domain, company or hosting provider.

**Search query example**  

![SMTP banner search](images/smtp_banner_search.png)


```
smtp.banner:fornex.cloud
```



Netlas CLI Tools:


```
netlas search "smtp.banner:fornex.cloud" -f json
```

Curl:


```

curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=smtp.banner%3Afornex.cloud&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.smtp.banner

```


**Code example (Netlas Python Library)**

![SMTP banner search Python](images/smtp_banner_search_python.png)



Run in command line:


```
python scripts/dfir/smtp_banner_search.py
```


Source code of scripts/dfir/smtp_banner_search.py:

```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `smtp.banner:fornex.cloud`
netlas_query = netlas_connection.query(query="smtp.banner:fornex.cloud")


# iterate over data and print: SMTP banner, URL, ISP
for response in netlas_query['items']:
    print (response['data']['smtp']['banner'])
    print (response['data']['uri'])
    print (response['data']['isp'])

```



## Search for domains that could potentially be used for phishing


One of the popular methods of scammers is to use domains that are very similar in spelling to the domains of well-known companies.

You can find such domains for a certain company using Netlas and fuzzy search.

![Domain fuzzy search](images/domain_fuzzy_search.png)


Open Whois domain search and enter company domain name + ~. For example:

```
domain:facebook.com~
``` 

[Try in Netlas](https://app.netlas.io/whois_domains/?q=domain%3Afacebook.com~&page=1&indices=)


![Domain fuzzy search import](images/domain_fuzzy_search_import.png)


After that click on the left icon, select the export file type, file names and the fields you want to save to the file. Click "Download" and wait for a while.


![Domain fuzzy search csv](images/domain_fuzzy_search_csv.png)


For example, you can select the CSV file format and the domain, expiration_date, status fields. Such a table can be conveniently viewed in Excel, Numbers or Google Docs.




## Favicon search

![Favicon search](images/favicon_search.png)

Searching for favicon.ico has three main uses. 

First, it allows you to find potentially related sites and subdomains. Try to find IP associated with Lidl shops:

```
http.favicon.perceptual_hash:003c7e72207e3c00
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.favicon.perceptual_hash%3A003c7e72207e3c00&page=1&indices=)

And also to find phishing sites that use the design of popular social networks, online stores, etc.

Second, it is a search for various IoT devices. Try to find HP products:


```
http.favicon.perceptual_hash:0c5ec8c181f37e2c
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.favicon.perceptual_hash%3A0c5ec8c181f37e2c&page=1&indices=)

Third, it searches for servers that have certain software launched on them. Try to find servers with PhpMyAdmin: 


```
http.favicon.perceptual_hash:00084e5e5fffff8d
```

[Try in Netlas](https://app.netlas.io/responses/?q=http.favicon.perceptual_hash%3A00084e5e5fffff8d&page=1&indices=)

There are three main ways to search by favicon hash in Netlas:

1. Click on the icon to the left of the search result.
2. Click on the favicon search button to the right of the search bar and paste the favicon link into the pop-up window.
3. Click on the favicon search button to the right of the search bar and upload the favicon file.


You can also use the following filters to search by favicon:

```
http.favicon.last_modified:
http.favicon.last_updated:
http.favicon.uri:
http.favicon.path:
```












## Search for domains associated with a specific subnet


![Subnet search](images/subnet_search.png)


Netlas domain search allows to get a complete list of domains associated with a specific IP address or range of addresses. Fox example:


```
a:"163.114.132.0/24"
```


[Try in Netlas](https://app.netlas.io/domains/?q=a%3A%22163.114.132.0%2F24%22&page=1&indices=)


API request example

Netlas CLI Tools:

```
netlas search -d domain a:\"163.114.132.0/24\"
```

Curl:

```
curl -X 'GET' \
  'https://app.netlas.io/api/domains/?q=a%3A%22163.114.132.0%2F24%22&source_type=include&start=0&fields=*' \
   -H 'accept: application/json' \
   -H 'X-API-Key: 'YOUR_API_KEY' | jq .items[].data.domain
 ```

**Code example (Netlas Python Library)**


![Subnet search](images/subnet_search_python.png)

Run in command line:

```
python scripts/dfir/subnet_search.py
```

Source code of scripts/dfir/subnet_search.py:


```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `a:"163.114.132.0/24"`
netlas_query = netlas_connection.query(query='a:"163.114.132.0/24"',datatype="domain")


# iterate over data and print: domain
for response in netlas_query['items']: 
    print (response['data']['domain'])

```



## Search for servers with malicious software

![Malware search](images/malware_search.png)


Netlas allows you to find servers that have various malware installed on them. You can find it by the presence of certain words in http.title or http.body, favicon hash, ssl and other parameters.

Here is an example of a query that will find servers that have GoFish (Open Source Phishing Framework) installed:


```
http.title:Gophish http.title:Login
```

Note that the technique of using the same operator twice (instead of an asterisk between two words) is used here. Sometimes this helps you get more search results.


Here are some more examples of similar requests:

```
http.title:CALDERA http.title:login
http.title:Deimos  http.title:C2  
```

**API request example**


Netlas CLI Tools:


```
netlas search "http.title:Gophish http.title:Login" -f json
```


Curl:


```
curl -X 'GET' \
  'https://app.netlas.io/api/responses/?q=http.title%3AGophish%20http.title%3ALogin&source_type=include&start=0&fields=*' \
  -H 'accept: application/json' \
  -H 'X-API-Key: YOUR_API_KEY' jq .items[].data.uri
```

**Code example (Netlas Python Library)**

![Malware search Python](images/malware_search_python.png)



Run in command line:


```
python scripts/dfif/malware_search.py
```


Source code of scripts/dfir/malware_search.py:


```python

import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from whois for "http.title:Gophish http.title:Login"
netlas_query = netlas_connection.query(query="http.title:Gophish http.title:Login")


# iterate over data and print: uri, title, country
for response in netlas_query['items']:
    print (response['data']['uri'])  
    print (response['data']['http']['title'])  
    print (response['data']['geo']['country'])

```





# Search for technologies and code examples

![Netlas for web designers](images/search_for_technologies_and_code_examples.png)

Netlas, unlike conventional search engines, allows you to search the entire HTML code rather than the text of the page. This allows you to find sites that use certain JavaScript libraries. This can help you find code samples suitable for your tasks and save your time.


For example, looking for sites that use an old obscure library to draw graphics:

```
http.body:kinetic.js
```

You can also see how different CSS frameworks are used on sites of certain themes and borrow good design ideas:

```
http.body:bootstrap.css http.title:travel
```


You can also filter sites that use specific frameworks and technologies by using tags:

```
tag.bootstrap:*
tag.angularjs:*
tag.wordpress:*
tag.nextjs:*
```





# Using Netlas.io for fun or netstalking


Netlas, like many other search engines, can be used without any specific purpose, and just explore with its help unexplored corners of the Internet, hoping to find something interesting there.

Here are some examples of search queries that will help you find what Google can't.


Search by text of Telnet servers banners (yes, they're still alive!):

```
telnet.banner:library
```


![Telnet banner](images/telnet_banner.png)

Search by text of FTP servers banners:

```
ftp.banner:*library*
```

Search for links to books and documents:

```
http.body:*rowling*pdf
```

Search for links to music and video:

```
http.body:*cats*mp4
```

Search for links to torrents file:

```
http.body:*cats*mp4
```

Keep in mind that Netlas does not censor the content it stores in its database in any way. If you find something illegal or immoral, you should complain to the hosting provider whose contacts are listed in the domain information.




# Common problems


## Error 429 - Too frequent requests


![Request limit](images/request_limit.png)

If your application includes multiple requests to the Netlas API, you may encounter this error:

```python
{'detail': 'Request was throttled. Expected available in 1 second.'}
```

One way to solve this problem is to use special Python libraries to configure time limits on query execution, such as [Limiter Package](https://pypi.org/project/ratelimit/). 


Here is an example of its use in code (limit of no more than 60 requests per minute). First, install package:

```
pip install ratelimit
```

And run scripts/common_problems/rate_limit.py:

```python
import netlas
from ratelimit import limits

# One second - one call
@limits(calls=1, period=1)
def netlas_query():
     apikey = "YOUR_API_KEY"

     # create new connection to Netlas
     netlas_connection = netlas.Netlas(api_key=apikey)

     # retrieve data from responses by query `cve.description:weblogic AND cve.has_exploit:true`
     netlas_query = netlas_connection.query(query="cve.description:weblogic AND cve.has_exploit:true")


     # iterate over data and print:  url, first CVE name first CVE description
     for response in netlas_query['items']:
        print (response['data']['uri'])
        print (response['data']['cve'][0]['name'])
        print (response['data']['cve'][0]['description'])

netlas_query()

```
Similar packages exist for other popular programming languages, as exceeding the request limit is a very common problem when working with almost most APIs. 


If you really need to make more than one enquiry per second, you can write to the sales team to solve your problem on a case-by-case basis - **sales@netlas.io**

## KeyError

![Key error](images/key_error.png)


Another common problem is the lack of a specific key in response for some servers. For example, ['data']['http']['title'] is quite often missing.

If the key is missing, the script stops executing. Standard error handling will help to avoid this. For example:

```python
try:
       print (response['data']['http']['title'])
    except:
        print ("no title")

```


## Automation of work with the list of requests

The main advantage of working with Netlas Python or the Netlas API versus just typing queries in the web version of Netlas.io is that you can save a tremendous amount of time typing one-size-fits-all queries. For example, you can quickly gather information about a long list of domains using very simple Python code.



Run in command line:


```
python scripts/common_problems/domain_list_search.py
```


Source code of scripts/common_problems/domain_list_search.py:


```python
import netlas

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)


# read file domains.txt line by line
with open("scripts/common_problems/domains.txt") as f:
    # save each line to domain variable
    for domain in f:
         # retrieve data from responses by query `domain:domainname`
        netlas_query = netlas_connection.query(
            query=f"domain:{domain}", datatype="domain-whois"
        )


        # iterate over data and print:  ip, isp
        for response in netlas_query['items']:
            print (response['data']['ip'])
            print (response['data']['isp'])

```

Similarly, you can work with a list of certificates, IP addresses, emails and whatever else you want.


An example of searching IP addresses from a URL-loaded list can be found in [Tor exit nodes search](#tor-exit-nodes-search).


## Saving data in CSV format

![Save data in CSV](images/save_data_in_csv.png)


By default, the Netlas Python Library returns data of type Dictionary (which is very similar to JSON). If you want to export the data to MS Excel or Google Sheets, one easy way to do it is to save it in CSV format.

Here's an example using the [CSV](https://docs.python.org/3/library/csv.html) package. Run scripts/common_problems/csv_export.py:



```python

import netlas
import csv

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.meta:nazar`
netlas_query = netlas_connection.query(query="http.meta:nazar")

with open('netlas_results.csv', 'w') as csv_file:
     # Create CSV writer object
     writer = csv.writer(csv_file, delimiter =';')


     # Create a list with data headers:
     header = ['IP', 'URL', 'Title']

     # Write headers to CSV file
     writer.writerow(header)

     # iterate over data and print: ip and url to CSV file
     for response in netlas_query['items']:

    # Create a list with one line of data:
          data = [response['data']['ip'], response['data']['uri']]
    # Write line to file
          writer.writerow(data)
     pass

```

You can open netlas_results.csv in Excel or any text editor.



## Saving data in other formats


Using Python, you can generate a wide variety of documents based on data from Netlas, inserting images, data visualizations, and customizing the layout. Here are some examples of useful packages.

[XLSXWriter](https://xlsxwriter.readthedocs.io/) - generate Microsoft Excel files.

[PyPDF](https://pypdf.readthedocs.io/en/stable/) - generate PDF files.

[PythonPPTX](https://python-pptx.readthedocs.io/en/latest/) - generate Microsoft Power Point Presentations.

[PythonDOCX](https://python-docx.readthedocs.io/en/latest/) - generate Microsoft Word files.





## Decoding Punycode domains


![ Decoding Punycode domains](images/punycode.png)



As mentioned above, Netlas does not store non-Latin domain names in their original encoding, but encodes them in Punycode. This is necessary for technical reasons, but it is completely inconvenient for human perception. 

But this problem is easily solved with a couple of lines of Python code.


Install [IDNA Python package](https://pypi.org/project/idna/):

```
pip install idna
```


And run scripts/common_problems/punycode.py in command line:

```python

import netlas
import idna

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `domain:*.中国  OR host:*.中国 `
netlas_query = netlas_connection.query(query="domain:*.xn--fiqs8s OR host:*.xn--fiqs8s")


# iterate over data and print: ip, domain (decoded from punycode)
for response in netlas_query['items']:
    print (response['data']['ip'])
    decoded_domain = idna.decode(str(response['data']['domain'][0]))
    print (decoded_domain)

```


## What to do if search queries don't return results?


Sometimes you may encounter a situation where no or very few results are found on query, although you are sure there should be many more. In this case we recommend you to experiment and try to change the queries a bit. 


1. Try adding two asterisks to your keyword. For example, domain:*github.com* returns 1,592,846 results. domain:githib.com - only 7911 results.

2. Try using different search filters to achieve the same goal. For example, compare results for uri:*github.com*, host:*github.com* and domain:*github.com*.

3. Do not use spaces in keywords. If you need to find the phrase "Hello world" in http.body, use the following query:


```
http.body:hello http.body:world
```

or

```
http.body:(hello AND world)
```


4. Refine your search filters as much as possible. For example, the query cve:*2023* will not return results. But the query cve.name:*2023* will return more than 28 million.


5. Try different tabs when working with the web app or different data types when working with the API. For example, when searching for domains, sometimes Host or Domain Whois (rather than response) works better.



## Removing html tags from http body

![Certificates search](images/htmltotext.png)

Key ['data']['http']['body'] by default returns the full body text of the web page, including all html tags. This format is not very easy to read. But you can easily remove them with the Python package [Html2text](https://pypi.org/project/html2text/).



Run in command line:


```
python scripts/common_problems/htmltotext.py
```


Source code of scripts/common_problems/htmltotext.py:



```python
import netlas
import html2text

apikey = "YOUR_API_KEY"

# create new connection to Netlas
netlas_connection = netlas.Netlas(api_key=apikey)

# retrieve data from responses by query `http.body:*phpMyAdmin*`
netlas_query = netlas_connection.query(query="http.body:*phpMyAdmin*")


# iterate over data and print: ip, web page text
for response in netlas_query['items']:
    print (response['data']['ip'])
    print (html2text.html2text(str(response['data']['http']['body'])))

```





## Working with very large amounts of data

![Datastore](images/datastore.png)

If you have a really big challenge ahead of you. For example, you need to collect data on hundreds of thousands of domains, then perhaps a more rational solution in terms of time and financial costs will be to buy a dataset (csv/json) and work with it on your own server.


In [Netlas Datastore](https://app.netlas.io/datastore/) you can find:

* Known domain names dataset (1,949,838,161 items)
* Forward DNS dataset (1,949,838,161 items)
* Known PTR records (1,135,524,997 items) - FREE
* Top 1,000,000 most common subdomains


and more.




## To be contininued... Stay tuned!

Want to know about Netlas Cookbook updates? 


👁️ Subscribe for updates


⭐️ Give us a star to show your appreciation


* [Twitter](https://twitter.com/Netlas_io)
* [Telegram](https://t.me/netlas)
* [Medium](https://netlas.medium.com/)
* [Linkedin](https://www.linkedin.com/company/netlas-io/)


Many thanks [@cyb_detective](https://twitter.com/cyb_detective) for help (https://cybdetective.com)

## License

![cc license](https://i.creativecommons.org/l/zero/1.0/88x31.png)

This work is licensed under a [CC0 1.0 Universal](LICENSE.md) license.






