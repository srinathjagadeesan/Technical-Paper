# Caching
process that stores multiple copies of data or files in a temporary storage location.


![Build Status](https://miro.medium.com/max/1360/0*oGWlpmZJ05JaWXQC.png)

Caching is a mechanism to improve the performance of any type of application. Technically, caching is the process of storing and accessing data from a cache. A cache is a software or hardware component aimed at storing data so that future requests for the same data can be served faster.

The main reason why caching was born is that accessing data from persistent memories takes a considerable amount of time. Thus, whenever data is retrieved or processed, it should be stored in a more efficient memory. We call such a memory cache, which can be thought of as a high-speed data storage layer whose primary purpose is to reduce the need to access slower data storage layers. To be cost-effective and efficient, caches must be relatively small, especially if compared to traditional memories. This is why they are usually implemented by using fast access hardware such as RAM (Random-Access Memory) plus a software component.

 It is possible to implement a mechanism to efficiently reuse previously retrieved or computed data. Whenever a new request arrives, the requested data is searched first in a cache. A cache hit occurs when the requested data can be found in a cache. On the contrary, a cache miss occurs when it cannot. Obviously, reading the required data from caches is assumed to be faster than recomputing the result or reading it from the original data store. So, the more requests can be served from a cache, the faster the system will be.

Caching is a fairly simple way to achieve performance improvements. This is especially true when compared to algorithm optimization, which is usually a much complex and time-consuming task.
* [Caching]https://www.youtube.com/watch?v=6FyXURRVmR0 

## Types of Caching
Although caching is a general concept, there a few types that stand out from the rest. They represent key concepts for any developers interested in understanding the most common approaches to caching, and they cannot be omitted. Let’s see them all.

### In-memory Caching
In this approach, cached data is stored directly in RAM, which is assumed to be faster than the typical storing system where the original data is located. The most common implementation of this type of caching is based on key-value databases. They can be seen as sets of key-value pairs. The key is represented by a unique value, while the value by the cached data.

Essentially, this means that each piece of data is identified by a unique value. By specifying this value, the key-value database will return the associated value. Such a solution is fast, efficient, and easy to understand. This is why it is usually the preferred approach by developers that are trying to build a caching layer.

### Database Caching
Each database usually comes with some level of caching. Specifically, an internal cache is generally used to avoid querying a database excessively. By caching the result of the last queries executed, the database can provide the data previously cached immediately. This way, for the period of time that the desired cached data is valid, the database can avoid executing queries. Although each database can implement this differently, the most popular approach is based on using a hash table storing key-value pairs. Just like seen before, the key is used to look up the value. Note that such type of cache is generally provided by default by ORM (Object Relational Mapping) technologies.

### Web Caching
This can be divided into two further subcategories:

#### 1. Web Client Caching
This type of cache is familiar to most Internet users, and it is stored on clients. Since it is usually part of browsers, it is also called Web Browser Caching. It works in a very intuitive way. The first time a browser loads a web page, it stores the page resources, such as text, images, stylesheets, scripts, and media files. The next time the same page is hit, the browser can look in the cache for resources that were previously cached and retrieve them from the user’s machine. This is generally way faster than download them from the network.

#### 2. Web Server Caching
This is a mechanism aimed at storing resources server-side for reuse. Specifically, such an approach is helpful when dealing with dynamically generated content, which takes time to be created. Conversely, it is not useful in the case of static content. Web server caching avoids servers from getting overloaded, reducing the work to be done, and improves the page delivery speed.

### CDN Caching
CDN stands for Content Delivery Network, and it is aimed at caching content, such as web pages, stylesheets, scripts, and media files, in proxy servers. It can be seen as a system of gateways between the user and the origin server, storing its resources. When the user requires a resource, a proxy server intercepts it and checks to see if it has a copy. If so, the resource is immediately delivered to the user; otherwise, the request is forwarded to the origin server. These proxy servers are placed in a vast number of locations worldwide, and user requests are dynamically routed to the nearest one. Thus, they are expected to be closer to end-users than origin servers, which implies a reduction in network latency. Plus, it also reduces the number of requests made to origin servers.
![CDN caching](https://www.cloudflare.com/img/learning/cdn/what-is-a-cdn/what-is-a-cdn.png)

| BASIS | CACHING |
| ------ | ------ |
| Basic | Caching fastens the data access speed of repeatedly used data. |
| Storage | Cache stores copy of the data. |
| Location | Cache is in processor, and can be also implemented with ram and disk. |
| Type | Cache is a fast disk and hence it is hardware. |
|Policy | Least recently used |
| Behavior | Read and write is same as the normal storage |


## Challenges 
Caching is by no means a simple practice, and there are inevitable challenges inherent in the subject. Let’s explore the most insidious ones.
#### 1. Coherence Problem
Since whenever data is cached, a copy is created, there are now two copies of the same data. This means that they can diverge over time. In a few words, this is the coherence problem, which represents the most important and complex issue related to caching. There is not a particular solution that is preferred over another, and the best approach depends on the requirements. Identifying the best cache update or invalidation mechanism is one of the biggest challenges related to caching and perhaps one of the hardest challenges in computer science.

#### 2. Choosing Data to Be Cached
Virtually any kind of data can be cached. This means that choosing what should reside in our cache and what to exclude is open to endless possibilities. Thus, it may become a very complex decision. As tackling this problem, there are some aspects to take into account. First, if we expect data to change often, we should not want to cache it for too long. Otherwise, we may offer users inaccurate data. On the other hand, this also depends on how much time we can tolerate stale data. Second, our cache should always be ready to store frequently required data taking a large amount of time to be generated or retrieved. Identifying this data is not an easy task, and you might risk filling our cache with useless data. Third, by caching large data, you may fill your cache very rapidly, or worse, using all available memory. If your RAM is shared between your application and your caching system, this can easily become a problem, which is why you should limit the amount of your RAM reserved for caching.

#### 3. Dealing with Cache-misses
Cache misses represent the time-based cost of having a cache. In fact, cache misses introducing latencies that would not have been incurred in a system not using caching. So, to benefit from the speed boost deriving from having a cache, cache misses must be kept relatively lows. In particular, they should be low compared to cache hits. Reaching this result is not easy, and if not achieved, our caching system can turn into nothing more than overhead.

# Conclusion
we looked at what is caching and why it has become increasingly important in computer science. At the same time, not underestimating the threats and risks coming with caching is critical as well. Implementing a properly defined caching system is not an easy task and requires time and experience. This is why knowing the most important types of cache is fundamental to design the right system. As shown, they can be reduced to a very limited set. Mastering them all should be the mission of every developer. In conclusion, caching is an unavoidable concept, and explaining its general concepts what this article was aimed at.

Thanks for reading! I hope that you found this helpful.


### Free reference, Hell Yeah!

These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen.
   *  Online editor: <https://dillinger.io/>.
   * [Basic Syntax]: <https://www.markdownguide.org/basic-syntax/#images-1>.
   * [Youtube Referance]: <https://www.youtube.com/watch?v=6FyXURRVmR0>.
   * [markdown-technical-writing]:<https://www.informationdevelopers.in/markdown-technical-writing/>.
   * [markdown-guides]: <https://guides.github.com/features/mastering-markdown/>.
   * [Artical]: <https://www.cloudflare.com/en-in/learning/cdn/what-is-caching/>.