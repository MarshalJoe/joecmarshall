---
title: "Contact Me"
layout: staticpage
---

<style type="text/css">
.contact-form {
    display: flex;
    flex-direction: column;
    max-width: 700px;
}

.contact-form label {
    font-size: 1.5rem;
    margin-top: 1.5rem;
}

.contact-form input,
.contact-form textarea {
    margin-top: 0.5rem;
    padding:1rem;
    font-size: 1.25rem;
}

.contact-form input::placeholder,
.contact-form textarea::placeholder {
    font-size: 1.25rem;
}
 
.contact-form button {
    margin-top: 1.5rem;
    padding: 1rem;
    font-size: 2rem;
    background-color: #aaa;
    color: white;
    border: none;
}

.contact-form button:hover {
    cursor: pointer;
}

</style>



<form class="contact-form" method="POST" action="https://api.formcake.com/api/form/ef1c9ab7-c54d-4bb9-a607-1fa5062edcab/submission">
    <label for="email">Email</label>
    <input placeholder="homer@compuglobalhypermega.net" required type="email" name="email" />
    <label for="message">Message</label>
    <textarea placeholder="Hmmm. Your ideas are intriguing to me and I wish to subscribe to your newsletter" required name="message" rows="10" cols="70"></textarea>
    <button type="submit" class="button">Submit</button>
</form>


























