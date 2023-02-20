# Gamemaker Multiline Text Field
An upgraded version of https://github.com/mh-cz/GameMaker-InputBox  
  
#### Usage
Basic  
```tf1 = new gmtf();```  
Using a struct to predefine style  
```tf1 = new gmtf({ w: 300, h: 100, text: "Hi there" });```  

- w - (real) text field width, default: 300
- h - (real) text field height, default: 110
- lh - (real) line height, default: 24
- padding - (struct) { top:real, bottom:real, left:real, right:real } text offset, default: { top: 4, bottom: 4, left: 4, right: 4 }
- char_limit - (real) maximum amount characters, default: infinity

		h: 110, 
		lh: 24, 
		text: "", 
		font: -1, 
		padding: { top: 4, bottom: 4, left: 4, right: 4 },
		c_bkg_unfocused:	{ c: c_gray, a: 1 }, 
		c_bkg_focused:		{ c: c_ltgray, a: 1 },
		c_text_unfocused:	{ c: c_black, a: 1 },
		c_text_focused:		{ c: c_black, a: 1 },
		c_selection:		{ c: c_blue, a: 0.275 },
		char_limit: infinity,
		letter_case: GMTF.DEFAULT,
		min_chw: 0,
		stoppers: " .,()[]{}<>?|:\\+-*/=" + chr_enter,


