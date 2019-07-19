---
title: "Adding a Loading Icon in Nuxt"
date: 2019-06-28T00:56:18-05:00
draft: false
tags: ["tutorial", "formcake"]
---

Today I'm going to discuss implementing a loading icon like you see in a lot of SPAs within the context of a Nuxt project I'm working on - Form Cast, a simple form backend-as-a-service.

### The Icon

My project at the moment is pretty spartanly designed, with a plain white background. For my loading icon, I wanted something with a flash of both activity and color. After surfing around, I decided on this (it's technically a typing activity icon, but who cares).

![](/images/loading.gif)

Let's go through the entirety of this (at the moment) dead simple page component. This is in our Nuxt app at `/pages/forms/index.vue`.

First in our `<script>` tag we're going to import our `Forms` component, our `listForms` function, which is simply an `axios` function that hits our API and returns an array of form `object`s, and our `mapState` function for our `vuex` store, which will allow us to pull our `userToken` out of local storage and make an API call to an authentication-protected resource.

```javascript
<script>
import Forms from '@components/Forms.vue'
import listForms from "@assetsPath/js/services/form/list.js"
import { mapState } from 'vuex';
```
Now into the next section, our actual component. We'll use our `default` layout and register our `Forms` component, will registering two `data` keys - `forms` (our array of form data) and `loading` (our loading icon UI variable, which we'll set initially to `true` since the page will initially be loading). We'll also use the `mapState` function to pull out our `userToken` JWT.

```javascript
export default {
    layout: 'default',

    components: {
        Forms,
    },

    data: function() {
        return {
            forms: null,
            loading: true
        }
    },

    computed: {
        ...mapState([
            "userToken"
        ])
    },
```

Now we can just call the `listForms` function, passing in our auth token, and once we get everything back, set loading to `false`. We'll need to make the `mounted()` function `async` so that we can use `await`. Then we can end things with a closing `</script>` tag.

```javascript
async mounted() {
    this.forms = await listForms(this.userToken);
    this.loading = false;
},
</script>
```

So now we have a `loading` state variable being set to `true` or `false` depending on our API call - we just need to build some display elements around it.

For this we can use Vue's `v-if`, simply showing the loading icon if `loading` is `true` and wrapping our actual content in a `v-else` `<div>`.

```html
<template>
    <section class="register-page container">
        <div class="loading" v-if="loading">
            <img class="loading-icon" src="/loading.gif">
        </div>
        <div v-else>
            <div class="section-title-pane">
                <h1 class="section-title">My Forms</h1>
            </div>
            <Forms v-bind:forms="forms" />
        </div>
    </section>
</template>
```

Putting it all together now. We'll also add in a nifty `flexbox` trick we can use to both horizontally and vertically center the loading icon, which we'll set to a width of `100px`.

```javascript
<script>
import Forms from '@components/Forms.vue'
import listForms from "@assetsPath/js/services/form/list.js"
import { mapState } from 'vuex';

export default {
    layout: 'default',

    components: {
        Forms,
    },

    data: function() {
        return {
            forms: null,
            loading: true
        }
    },

    computed: {
        ...mapState([
            "userToken"
        ])
    },

    async mounted() {
        this.forms = await listForms(this.userToken);
        this.loading = false;
    },
}
</script>
<template>
    <section class="register-page container">
        <div class="loading" v-if="loading">
            <img class="loading-icon" src="/loading.gif">
        </div>
        <div v-else>
            <div class="section-title-pane">
                <h1 class="section-title">My Forms</h1>
            </div>
            <Forms v-bind:forms="forms" />
        </div>
    </section>
</template>

<style lang="scss">
.loading {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height:500px;
}

.loading-icon {
    width: 100px;
}
</style>
```

And we're done!

![](/images/formcast-loading.png)

### Subscribe for more updates

Want to hear more about Form Cast as it goes from glint-in-its-founders-eyes to a real-live business? Subscribe for notification updates below.

<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
    #mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }

    #mc_embed_signup #mce-success-response {
        color: gray;
    }

    #mc_embed_signup div#mce-responses {
        margin: 0;
        padding: 0;
    }
    /* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
       We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form style="padding:0" action="https://jobletter.us9.list-manage.com/subscribe/post?u=50452eee01aae18a82d9dd092&amp;id=3dce412832" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
<div class="mc-field-group">
    <label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
</label>
    <input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
    <div id="mce-responses" class="clear">
        <div class="response" id="mce-error-response" style="display:none"></div>
        <div class="response" id="mce-success-response" style="display:none"></div>
    </div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_50452eee01aae18a82d9dd092_3dce412832" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>
<script type='text/javascript' src='//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js'></script><script type='text/javascript'>(function($) {window.fnames = new Array(); window.ftypes = new Array();fnames[0]='EMAIL';ftypes[0]='email';fnames[1]='FNAME';ftypes[1]='text';fnames[2]='LNAME';ftypes[2]='text';}(jQuery));var $mcj = jQuery.noConflict(true);</script>
<!--End mc_embed_signup-->

