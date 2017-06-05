# Apps-Script-htmlparser2-library
A browserified version of fb55/htmlparser2 modified to work in Google Apps Script
  
This is a library of the htmlparser2 module that has been ran through browserify and modified for Apps Script.  
You can either include the source code of this library or you can link to it with the ID:  

`1TLbGgQBCztnB0lOhcTYKg2UpXtpdDwocvfcx44w1tqFnHDJC5ZXy_BDo`  

Example of use:
  
     function myFunction() {   
      var htmlparser = htmlparser2.init();
      var parser = new htmlparser.Parser({
        onopentag: function(name, attribs){
          if(name === "div"){
            Logger.log("found div");
          }
        },
        ontext: function(text){
          Logger.log("-->" + text); 
        },
        onclosetag: function(tagname){
          if(tagname === "div"){
            Logger.log("end div");
          }
         }
      }, {decodeEntities: true});
      parser.write('<div>outer<div>inner<br>inner 2</div></div>');
      parser.end();  
    }
      
    
See https://github.com/fb55/htmlparser2 for more info on this library.
