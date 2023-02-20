# Gamemaker Multiline Text Field
An upgraded version of https://github.com/mh-cz/GameMaker-InputBox  
  
### Creating a text field
Basic  
```tf1 = new gmtf();```  
Using a struct to define style  
```tf1 = new gmtf({ w: 300, h: 100, text: "Hi there", c_text_unfocused: { c: white, a: 1 } });```  
  
### Style variables
```w``` - (real) text field width, default: ```300```  
```h``` - (real) text field height, default: ```110```  
```lh``` - (real) line height, default: ```24```  
```padding``` - (struct) text offset from borders, default: ```{ top: 4, bottom: 4, left: 4, right: 4 }```  
```char_limit``` - (real) maximum amount characters, default: ```infinity```  
```font``` - (font) font, default: ```-1``` (no font set)  
```text``` - (string) set text, default ```""``` (no text)  
```letter_case``` - (GMTF enum) transform every character to upper or lower case, default ```GMTF.DEFAULT```  
```min_chw``` - (real) minimal width of each character, default: ```0``` (WARNING: values other than ```0``` will make the text render by characters instead of by lines)  
```stoppers``` - (string) characters which stop the cursor while moving using ctrl, default: ```" .,()[]{}<>?|:\\+-*/="```  
#### Colors
```c_bkg_unfocused``` - (struct) unfocused background color and alpha, default: ```{ c: c_gray, a: 1 }```  
```c_bkg_focused``` - (struct) focused background color and alpha, default: ```{ c: c_ltgray, a: 1 }```  
```c_text_unfocused``` - (struct) unfocused text color and alpha, default: ```{ c: c_black, a: 1 }```  
```c_text_focused``` - (struct) focused text color and alpha, default: ```{ c: c_black, a: 1 }```  
```c_selection``` - (struct) mouse selection color and alpha, default: ```{ c: c_blue, a: 0.275 }```  
  
Style can be altered later by calling ```tf1.set_style(<style_struct>)```  
WARNING: Do not run style changes (except colors) every step since it has to update every single character and line which will cause lag  


