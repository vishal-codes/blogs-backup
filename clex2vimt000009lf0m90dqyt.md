---
title: "Revolutionizing Web Development with Progressive Web Applications"
seoTitle: "React to PWA"
seoDescription: "Revolutionizing Web Development with Progressive Web Applications. Convert your existing React website to a Progressive  Web Application."
datePublished: Mon Mar 06 2023 17:10:12 GMT+0000 (Coordinated Universal Time)
cuid: clex2vimt000009lf0m90dqyt
slug: react-to-pwa-basic
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678122444702/5e025084-2ba7-4858-8036-db1c8c9137fe.webp
tags: javascript, web-development, reactjs, pwa, wemakedevs

---

As web technology advances, so does the need for faster, more reliable, and more engaging web experiences. One solution that has been gaining traction in recent years is Progressive Web Applications (PWAs). PWAs are web applications that provide an app-like experience with native app features, such as push notifications and offline access, without the need for users to download a separate app. In this article, I'll explore the basics of PWA development and show you some hacks to quickly turn your React website into a fully functioning PWA. If you want in-depth knowledge on PWAs then I'll recommend this free [resource](https://web.dev/learn/pwa/).

### **Benefits of PWAs**

PWAs have numerous benefits for both developers and users. For developers, PWAs are easier and more cost-effective to develop compared to native apps. They also offer more flexibility, as they can be updated without requiring users to download new versions. For users, PWAs offer fast and responsive performance, even on slow or unreliable networks. They also take up less storage space on users' devices and don't require users to download and install anything.

### **PWA Features**

To create a PWA, you need to ensure that it meets certain requirements. Some key features of PWAs include:

* **App shell architecture**: This is the basic HTML, CSS, and JavaScript code that provides the framework for your PWA. It's the foundation upon which you'll build the rest of your app.
    
* **Service workers**: These are scripts that run in the background and handle tasks such as caching, push notifications, and offline access.
    
    [More about Service workers](https://web.dev/learn/pwa/service-workers/).
    
* **Manifest file**: This file contains metadata about your app, such as its name, icon, and colour scheme. It's used by browsers to display your app on users' devices.
    
    [More about Web app manifest](https://web.dev/learn/pwa/web-app-manifest/).
    

### **Creating a PWA**

Let's convert a React website into a PWA. I'll be using one of my react projects the [Bookmark Manager](https://github.com/Evozone/Bookmark-Manager) to convert it into a PWA. You can follow the same steps to convert your own React project into a PWA.

1. **Set up your app shell**: This involves creating the basic HTML, CSS, and JavaScript code for your app which should already be present in your project. Additionally, you can create an `offline.html` file to enhance the user experience even when they're offline. This file can occupy the screen if the user is offline and improve the overall user experience of your PWA.
    
    This is how your public folder should look like
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678110175106/0bdbcb4a-d7d0-46bc-a2df-4d44cda6ffdb.png align="center")
    
    You can use the content of `offline.html` as well
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta http-equiv="X-UA-Compatible" content="IE=edge" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <title>U r offline :(</title>
            <style type="text/css">
                html {
                    margin: 20px;
                }
                body {
                    height: 90vh;
                    font-family: 'Montserrat', -apple-system, BlinkMacSystemFont,
                        'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell',
                        'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
                    font-size: 40px;
                    margin: auto;
                    background: #141414;
                    color: rgb(178, 178, 178);
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    text-align: center;
                    justify-content: center;
                    max-width: 800px;
                }
            </style>
        </head>
        <body>
            <p>
                You are offline. You will need an active internet connection to
                access your bookmarks 🔖
            </p>
            <div class="svg-container">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    data-name="Layer 1"
                    width="100%"
                    height="100%"
                    viewBox="0 0 626.47693 457.63821"
                    xmlns:xlink="http://www.w3.org/1999/xlink"
                >
                    <circle cx="167.36133" cy="184.72675" r="161" fill="#f2f2f2" />
                    <path
                        d="M719.69269,403.26144l-35.39595,30.42862-55.47525,47.672-7.49829,6.44653a6.8008,6.8008,0,0,0-2.37431,4.68328,6.89054,6.89054,0,0,0,.79663,3.76454,6.82122,6.82122,0,0,0,.8404,1.21719l4.02193,4.68382,6.12263,7.12247c.113.126.21915.24352.34039.363a6.86525,6.86525,0,0,0,9.32664.35954l62.90579-54.05126,35.47044-30.48746a6.86477,6.86477,0,0,0,.72225-9.66692l-2.14032-2.48871-7.9978-9.30954a6.84536,6.84536,0,0,0-9.66518-.73707Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#7bfff6"
                    />
                    <circle
                        cx="459.90632"
                        cy="100.04778"
                        r="56.43171"
                        fill="#7bfff6"
                    />
                    <path
                        d="M750.81479,540.37146V670.07578a6.86023,6.86023,0,0,0,6.85374,6.85374h15.563a6.86023,6.86023,0,0,0,6.85374-6.85374V540.37146a6.86027,6.86027,0,0,0-6.85374-6.85374h-15.563A6.86027,6.86027,0,0,0,750.81479,540.37146Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <path
                        d="M717.92747,540.37146V670.07578a6.85329,6.85329,0,0,0,6.85373,6.85374h15.563a6.86022,6.86022,0,0,0,6.85373-6.85374V540.37146a6.86027,6.86027,0,0,0-6.85373-6.85374h-15.563A6.85334,6.85334,0,0,0,717.92747,540.37146Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <path
                        d="M699.01269,346.17449l.0587-2.10884c-3.92319-.10915-7.382-.35525-9.981-2.254a6.48255,6.48255,0,0,1-2.51094-4.77475,3.70559,3.70559,0,0,1,1.21557-3.05206c1.72527-1.457,4.50136-.98543,6.52474-.05766l1.74484.80008-3.346-24.45247-2.08927.28626,2.84611,20.8001c-2.74932-.80833-5.29682-.46028-7.04166,1.01323a5.76869,5.76869,0,0,0-1.96159,4.73665,8.57523,8.57523,0,0,0,3.37435,6.40376C691.18588,345.95517,695.52559,346.07667,699.01269,346.17449Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <rect
                        x="418.02782"
                        y="91.17387"
                        width="11.35768"
                        height="2.10884"
                        fill="#2f2e41"
                    />
                    <path
                        d="M761.41151,413.7988l1.94,46.637,3.02632,73.0819.41136,9.87992a6.80086,6.80086,0,0,0,2.20358,4.766,6.89057,6.89057,0,0,0,3.448,1.70815,6.82144,6.82144,0,0,0,1.47608.09493l6.16847-.25312,9.38424-.39013c.16887-.01055.32693-.021.4958-.04215a6.86525,6.86525,0,0,0,6.06292-7.09623l-3.42686-82.867-1.94-46.73194a6.86479,6.86479,0,0,0-7.13845-6.55847l-3.27962.13708-12.26279.50611a6.84534,6.84534,0,0,0-6.569,7.12789Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#7bfff6"
                    />
                    <path
                        d="M756.67743,417.74232v35.85031a6.84924,6.84924,0,0,0,6.67405,6.84319.97038.97038,0,0,0,.17969.01055h25.3061a6.56839,6.56839,0,0,0,1.21248-.116,6.75521,6.75521,0,0,0,2.55162-1.01227,6.88294,6.88294,0,0,0,3.08964-5.7255V417.74232a19.53034,19.53034,0,0,0-19.50679-19.50678,19.07291,19.07291,0,0,0-3.986.41124A19.53758,19.53758,0,0,0,756.67743,417.74232Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <path
                        d="M682.74132,432.70456a6.77705,6.77705,0,0,0,1.2547,2.33029l16.0274,19.58054a5.68008,5.68008,0,0,0,.98028.97012,6.85,6.85,0,0,0,8.66757-.01056l27.74187-22.70171a19.50772,19.50772,0,1,0-24.71608-30.18808L684.9557,425.38688A6.8905,6.8905,0,0,0,682.74132,432.70456Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <path
                        d="M730.01151,287.79969a8.73,8.73,0,0,1-17.31961-1.42791,1.50771,1.50771,0,0,0-2.94642-.39876c-2.0663,5.31384-7.37588,8.9494-12.92819,9.7288a16.277,16.277,0,0,1-15.29012-6.86947,17.90918,17.90918,0,0,1-2.33173-16.97942,20.22333,20.22333,0,0,1,12.81474-12.01848,21.20294,21.20294,0,0,1,20.15066,4.65893,1.514,1.514,0,0,0,2.50708-.6619c2.81818-14.89737,12.95406-27.83881,26.39981-34.71091,13.7412-7.02309,30.12465-6.38621,43.71258.70728A48.85756,48.85756,0,0,1,801.909,244.46591c5.30753,7.40537,8.03464,16.17671,10.59773,24.815,4.48707,15.12262,10.055,33.2368,25.97621,39.95121A28.17607,28.17607,0,0,0,877.487,283.29137a1.5009,1.5009,0,0,0-3,0,25.08244,25.08244,0,0,1-34.46925,23.352c-7.37984-2.93493-12.72124-9.311-16.43889-16.119-4.17392-7.64353-6.37488-16.08552-8.87548-24.37131-2.54575-8.43537-5.49357-16.96212-10.84593-24.07533a52.25107,52.25107,0,0,0-17.24236-14.67152c-13.63878-7.23918-29.90683-8.398-44.15591-2.24461a53.3703,53.3703,0,0,0-29.34806,32.496,47.67183,47.67183,0,0,0-1.336,5.3764l2.50708-.6619a24.39728,24.39728,0,0,0-20.50127-6.0269,23.05026,23.05026,0,0,0-16.46338,12.37746,20.87081,20.87081,0,0,0,.64309,20.13665c3.54908,5.95628,9.97143,10.14174,17.02294,9.98359a19.49021,19.49021,0,0,0,17.65477-12.07232l-2.94642-.39876a11.72671,11.72671,0,0,0,23.21244,2.22542c.40454-1.88263-2.4868-2.68711-2.89283-.79751Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#2f2e41"
                    />
                    <polygon
                        points="516.361 341.727 403.361 341.727 439.361 182.727 478.361 182.727 516.361 341.727"
                        fill="#2f2e41"
                    />
                    <path
                        d="M548.786,555.20605c20.66809-.58645,40.64336-8.51888,56.65-21.49681a90.95513,90.95513,0,0,0,32.00273-51.74665,97.24881,97.24881,0,0,0-7.703-61.51576,90.051,90.051,0,0,0-44.1148-42.78719,96.28983,96.28983,0,0,0-60.854-6.40643c-2.55469.59033-5.07733,1.30361-7.56834,2.12119-2.27612.74706-1.30155,4.35918.99406,3.60573,19.11574-6.274,40.03052-5.52437,58.91352,1.238a87.17555,87.17555,0,0,1,45.63872,37.11046,93.54677,93.54677,0,0,1,12.26169,58.51992,86.47957,86.47957,0,0,1-26.39119,52.09c-14.22912,13.589-32.928,22.81535-52.54505,25.02487-2.42024.2726-4.85.4343-7.28433.50337-2.40118.06814-2.41105,3.80771,0,3.7393Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#3f3d56"
                    />
                    <path
                        d="M512.99652,338.37993,479.41626,366.9314c-2.19525,1.8665-4.79986,3.79293-5.3929,6.79753a7.55479,7.55479,0,0,0,2.62247,6.84572c2.18018,2.07325,4.95563,3.39114,7.56418,4.82544l9.75961,5.36628,21.688,11.92507c2.11,1.16016,3.9988-2.06777,1.88729-3.22878-11.75274-6.4622-23.6801-12.68421-35.28365-19.4098-1.75678-1.01825-4.51921-2.66353-4.6241-4.97689-.11236-2.47834,3.269-4.51915,4.89613-5.90262l15.60773-13.2704L515.6406,341.024c1.836-1.561-.81991-4.19508-2.64408-2.64409Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#3f3d56"
                    />
                    <path
                        d="M382.69843,264.46c-25.15545,4.28174-48.19715,17.42084-65.51879,36.041-17.4575,18.76623-28.52929,43.104-30.18175,68.75516a120.01711,120.01711,0,0,0,20.0241,73.84419,111.13416,111.13416,0,0,0,61.28921,44.67691c24.60463,7.17929,51.4787,6.563,75.46927-2.66813,3.02-1.16206,5.97968-2.46883,8.88269-3.8976,2.65259-1.30552.83858-5.55146-1.8367-4.23477-22.27741,10.96426-47.9648,13.6558-72.20647,8.64933-24.32149-5.023-46.5763-18.07313-62.17225-37.477a115.44839,115.44839,0,0,1-25.07816-69.39689,106.72648,106.72648,0,0,1,23.26518-68.20682c15.04414-19.06025,36.30284-33.56042,59.894-39.64427,2.91054-.75059,5.85185-1.36731,8.81469-1.87162,2.92252-.49744,2.28953-5.06895-.645-4.56946Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#3f3d56"
                    />
                    <path
                        d="M463.83436,523.25034l36.11052-40.68252c2.36066-2.65955,5.21123-5.46294,5.41766-9.23688.18038-3.29771-1.80124-6.06811-4.38552-7.91319-3.02183-2.15747-6.64079-3.2892-10.07586-4.592l-12.852-4.87419-28.56-10.83154c-2.77852-1.05377-4.5299,3.2166-1.74935,4.27114,15.47665,5.86961,31.12525,11.41559,46.465,17.63281,2.32244.94129,5.982,2.47534,6.50917,5.28419.56481,3.00918-3.2152,6.08632-4.965,8.05761l-16.78376,18.90878-18.81815,21.20075c-1.97433,2.2243,1.72556,4.985,3.68717,2.775Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#3f3d56"
                    />
                    <path
                        d="M912.31912,678.81911H574.84786a.91934.91934,0,0,1,0-1.83869H912.31912a.91935.91935,0,1,1,0,1.83869Z"
                        transform="translate(-286.76153 -221.18089)"
                        fill="#3f3d56"
                    />
                </svg>
            </div>
        </body>
    </html>
    ```
    
    Output
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678110052988/95980314-de8e-4d79-b541-f2d8b788ff6e.png align="center")
    
    While I've used an SVG from [unDraw](https://undraw.co/illustrations), feel free to use any other SVG of your choice to enhance the look and feel of the offline page of your PWA.
    
2. **Create & Register a service worker**: This is done using JavaScript code that specifies the files to cache and the tasks to handle. In the public folder create a file named `serviceWorker.js`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678108712171/0085e368-16c8-4812-9f9b-cf11724ed377.png align="center")
    
    Contents of `serviceWorker.js`
    
    ```javascript
    const CACHE_NAME = 'version-1.0';
    const urlsToCache = ['index.html', 'offline.html'];
    
    const self = this;
    
    self.addEventListener('install', (event) => {
        event.waitUntil(
            caches.open(CACHE_NAME).then((cache) => {
                console.log('Opened cache');
                return cache.addAll(urlsToCache);
            })
        );
    });
    
    self.addEventListener('fetch', (event) => {
        event.respondWith(
            caches.match(event.request).then(() => {
                return fetch(event.request).catch(() =>
                    caches.match('offline.html')
                );
            })
        );
    });
    
    self.addEventListener('activate', (event) => {
        const cacheWhitelist = [];
        cacheWhitelist.push(CACHE_NAME);
        event.waitUntil(
            caches.keys().then((cacheNames) =>
                Promise.all(
                    cacheNames.map((cacheName) => {
                        if (!cacheWhitelist.includes(cacheName)) {
                            return caches.delete(cacheName);
                        }
                    })
                )
            )
        );
    });
    ```
    
    Here `self` is the service worker itself. It enables the application to listen to [life cycle events](https://web.dev/service-worker-lifecycle/) and do something in return.
    
    Now to register this service worker paste the below script tag just before the closing body tag in `index.html`
    
    ```xml
    <script>
        if ('serviceWorker' in navigator) {
            console.log('Will service worker register?');
            navigator.serviceWorker
                .register('/serviceWorker.js')
                .then(function (reg) {
                    console.log('Yes it did.');
                })
                .catch(function (err) {
                    console.log("No it didn't. This happened: ", err);
                });
        }
    </script>
    ```
    
3. **Add a manifest file**: This file should contain metadata about your app, such as its name, icon, and colour scheme. You can generate icons using this [website](https://maskable.app/editor). If you have used `create-react-app` while setting up your react project then there must be a file named `manifest.json` in the public directory, if there isn't then create the same. At this stage, your public folder should look something like this
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678110763971/6b0407fd-9163-458e-957b-555e1c1a4a40.png align="center")
    
    Content of `manifest.json`. Customize the values as per your application needs. [About the properties](https://developer.mozilla.org/en-US/docs/Web/Manifest).
    
    ```json
    {
        "theme_color": "#7bfff6",
        "background_color": "#000",
        "display": "standalone",
        "scope": "/",
        "start_url": "/",
        "name": "Bookmark Manager",
        "short_name": "Bookmark Manager",
        "description": "Manage your Bookmarks seamlessly from any device",
        "icons": [
            {
                "src": "favicon.ico",
                "sizes": "48x48",
                "type": "image/x-icon"
            },
            {
                "src": "/icon-192x192.png",
                "sizes": "192x192",
                "type": "image/png"
            },
            {
                "src": "/icon-256x256.png",
                "sizes": "256x256",
                "type": "image/png"
            },
            {
                "src": "/icon-384x384.png",
                "sizes": "384x384",
                "type": "image/png"
            },
            {
                "src": "/icon-512x512.png",
                "sizes": "512x512",
                "type": "image/png",
                "purpose": "maskable"
            }
        ]
    }
    ```
    
4. **Test your PWA**: Use Google's Lighthouse tool to test your PWA.
    
    ![a gif showing lighthouse report.](https://cdn.hashnode.com/res/hashnode/image/upload/v1678121681510/4d2d837d-3610-4ec4-b609-8c7d5502896f.gif align="center")
    

### **Conclusion**

PWAs are a powerful and flexible way to provide users with an app-like experience on the web. By following the steps outlined above, you can create your own PWA and offer users fast, reliable, and engaging web experiences. As web technology continues to evolve, PWAs will likely become an even more important part of web development.