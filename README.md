# standalone-auto-complete
This is the fully customizable auto complete javascript search box plugin especially for standalone input search like on Musixmatch and Melomap.com. Amazing feature of this plugin is you can choose the search result by pressing up and down arrow keys on keyboard. So this support selecting by keyword as well. This plugin is suitable if you want to develop standlone search box like search engine with auto complete feature and beautiful ui include images. Design is fully customizable. So you can design it to whatever amazing design you want.

###These are the screenshots
![example screenshots](https://github.com/waiyanhein/standalone-auto-complete/blob/master/search_image.png)

>As you can see in screenshot, you can customize the UI design by overriding CSS and HTML or in Javascript code.

###Dependencies
Only jquery is required to use this plugin.

###Usage
1. Include the standalone-auto-complete.min.css file
2. Include the jquery file
3. Include the standalone-auto-complete.min.js file
4. Then follow the instructions below

#####Include the html

```
<form action="url/to/search">
    <div class="standlone-search-container">
        <div class="standalone-input-holder">
            <input type="text" autocomplete="off" name="keyword" class="standlone-input" />
        </div>
          <div class="standlone-result-container">
        </div>
    </div>
</form>
```
#####Initialize in javascript like this
```
$(function(){	
	$('.standlone-input').standaloneAutoComplete({ url : "url to fetch data from server" });
})
```

#####From server, return JSON in the format in below example
```
[
  {
    'url':'http://example.com?id=1',
    'image_url':'url/to/image',
    'first_title':'Bill Gates',
    'second_title':'CEO of Microsoft'
  },
  {
    'url':'http://example.com?id=2',
    'image_url':'url/to/image',
    'first_title':'Mark Zuckerberg',
    'second_title':'CEO of Facebook'
  },
  {
    'url':'http://example.com?id=3',
    'image_url':'url/to/image',
    'first_title':'Drew Houston',
    'second_title':'CEO of Dropbox'
  }
]
```
#####To filter the data by using keyword entered in the input catch the keyword with "keyword" field using HTTP Get from server

#####Catching in PHP
```
$keyword = $_GET['keyword'];
```
#####In asp.net mvc bind the data in action like this
```
public JsonResult GetData(string keyword)
{
   if(!String.IsNullOrEmpty(keyword)
   {
       //continue
   }
}
```
#####*That's it! You are done. Customize the design by overriding the css or use the javascript options below.*

####Options
######search_start_limit : default value is 2
That is the setting for the start when the limited number of word is enterd. For example, it you set it to 3 and it you enter only two words in search box, it will not start working.
######url
This is the url to detch data from server. This field is essential. Use like in the above example.
######s_item_border : default value is "2px solid #6699ff"
This is the default value for selected item border. Selected item mean when you choose item from result using up or down arrow key on keyboard, current item will be hightlighted with the border in this css value. Note you have to set the full css rule as mentioned default value.
######item_border : default value is "1px solid #cccccc"
This is the border css value for searched item border. Note: set the full css rule.
######item_border_radius: default value is "5px"
This is the value for border radius for individual item.
######content_bg_color: default value is ""#f2f2f2""
This is the background color for the search result container and its related. 
######content_border_radius: default value is ""10px""
This is the border radius for result container, its related.
######item_bg: default valus is "#ffffff"
This is the backgorund color for the individual item. 
