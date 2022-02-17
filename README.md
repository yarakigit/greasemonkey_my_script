# greasemonkey_my_script
---
## firefox extention greasemonkey user script
- [Greasemonkey](https://addons.mozilla.org/ja/firefox/addon/greasemonkey/)
---
### exapme1 : Nagasaki University wifi automation  
~~~

// ==UserScript==
// @name  Nagasaki University wifi automation
// @version  1
// @grant    none
// @match    http://wlc.cc.nagasaki-u.ac.jp/fs/*
// @exclude  *logout.html*
// ==/UserScript==

console.log("launch");
var now_url = location.href;
if (!(now_url.indexOf('logout.html') !== -1)) {
    console.log("auto login")
    //ID
    var frm = document.getElementsByName("username")[0];
    frm.value = "hoge";
    //Passward
    var pass = document.getElementsByName("password")[0];
    pass.value = "piyo"; 
  
  	var pre_button = document.getElementsByTagName("body")[0];//redirect_url//buttonClicked
    console.log(pre_button);
    pre_button.onload();	
  		
    //Submit button
    var button = document.getElementsByName("Submit")[0];
    console.log(button)
    button.onclick();
  
}
else{
    console.log("nothing");
}
console.log("finish");

~~~
