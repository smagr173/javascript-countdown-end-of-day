# Mail2Mail
Get notified via email when your mail or packages arrive<br/>
- Implemented using HTML, CSS, PHP, and JavaScript
- Utilized PHPMailer (public repository) for email features

```javascript
// The end of the current day in UTC format, includes the day of month, etc
var countDown = new Date();
countDown.setHours(24, 0, 0, 0); // Set it to the start of the next day

// Holds just the current time, rather than the whole datetime string
var later = countDown.getTime();

// timeLeft function gets called every 1 sec, amount left is displayed
var x = setInterval(timeLeft, 1000);

function timeLeft() {
   // Get today's date and time
  var now = new Date().getTime();
    
  // Find the distance between now and the end of the current day
  var distance = later - now;
    
  // Time calculations for hours, minutes and seconds
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);
  
  // Output
  document.getElementById("demo").innerHTML = "Update in " + hours + "h "
  + minutes + "m " + seconds + "s ";
  
  // If the countdown is over (it's midnight) then stop timer and output message
  if (distance <= 0) {
    clearInterval(x);
    document.getElementById("demo").innerHTML = "Update in progress..";
    location.reload();
  }
}
```
