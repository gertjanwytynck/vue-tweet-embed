# vue-tweet-embed

Embed tweets in your vue.js app.  
Inspired by https://github.com/capaj/react-tweet-embed

## Install
```
npm install vue-tweet-embed
```

## Supported components
Currently only Tweet and Moment components are supported form Twitter's widget API.  
Components can be imported in one statement:
```javascript
import { Tweet, Moment } from 'vue-tweet-embed'
```
or individually
```javascript
import Tweet from 'vue-tweet-embed/tweet'
import Moment from 'vue-tweet-embed/moment'
```

Moment component can be used the same way Tweet component is used (see below).
## Quickstart

```javascript
import { Tweet } from 'vue-tweet-embed'

<Tweet :id="'692527862369357824'"></Tweet>
<Tweet :id="'14'"></Tweet>	// test tweet not available or deleted
```

You don't have to put `//platform.twitter.com/widgets.js` script in your index.html as this lib will
put it there if `twttr` is not found on window.  


## Using Options

```javascript
<Tweet :id="'783943172057694208'" :options="{ cards: 'hidden' }"/>
<Tweet :id="'771763270273294336'" :options="{ theme: 'dark' }"/>
```

Embedded-Tweet Options Reference:
https://dev.twitter.com/web/embedded-tweets/parameters


## Showing a placeholder while the tweet is being loaded

To show some content to the user while the tweet is being loaded, just put it inside the Tweet
component. Placeholder content will be removed automatically once the tweet has finished loading.

```javascript
<Tweet :id="'783943172057694208'"/><div class="spinner"></div></Tweet>
```


## Show some text if the tweet is unavailable

Tweets that could not be loaded can be replaced with custom text.
A custom class can be specifier as well.
```javascript
<Tweet :id="'14'" error-message="This tweet could not be loaded" error-message-class="tweet--not-found"></Tweet>
```
