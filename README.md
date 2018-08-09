# mailchimp-popup-form-onclick
Show Mailchimp popup form on button click

Create a button or link with the id of "open-popup".

```javascript
<script>
  var chimpScript = document.createElement("script");
  chimpScript.src = '//downloads.mailchimp.com/js/signup-forms/popup/embed.js';
  chimpScript.setAttribute('data-dojo-config', 'usePlainJson: true, isDebug: false');

  function showMailingPopUp() {
    require(["mojo/signup-forms/Loader"], function(L) { L.start({"baseUrl":"XXX","uuid":"XXX","lid":"XXX"}) })
    document.cookie = 'MCPopupClosed=;path=/;expires=Thu, 01 Jan 1970 00:00:00 UTC;';
    document.cookie = 'MCPopupSubscribed=;path=/;expires=Thu, 01 Jan 1970 00:00:00 UTC;';
  };
     
  window.onload = function() {
    document.body.appendChild(chimpScript);
    document.getElementById("open-popup").onclick = function() { showMailingPopUp(); };
  }
</script>
```
