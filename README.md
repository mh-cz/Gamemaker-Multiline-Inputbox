# Gamemaker Multiline Text Field
An upgraded version of https://github.com/mh-cz/GameMaker-InputBox  
  
### Can do:
Ctrl+C - copy  
Ctrl+V - paset  
Ctrl+X - cut  
Tab - switch to next tf  
Shift+Tab - switch to previous tf  
Left, Right, Up, Down arrows - move cursor  
LMB click - move cursor  
LMB click and drag - select text  
Left/Right+Ctrl - skip words  

### Creating
```<text_field_variable> = new gmtf(style_struct=undefined)```  
Basic:  
```tf1 = new gmtf();```  
Using a struct to define style:  
```tf1 = new gmtf({ w: 450, h: 90, text: "Hi there", c_text_unfocused: { c: white, a: 1 } });```  
### Drawing
```<text_field_variable>.draw(x, y, gui_ev=true)```  
In Draw GUI event:  
```tf1.draw(50, 60);```  
In a Draw event  
```tf1.draw(50, 60, false);```  
  
### Style variables
```w``` - (real) text field width, default: ```300```  
```h``` - (real) text field height, default: ```110```  
```lh``` - (real) line height, default: ```24```  
```padding``` - (struct) text offset from borders, default: ```{ top: 4, bottom: 4, left: 4, right: 4 }```  
```char_limit``` - (real) maximum amount characters, default: ```infinity```  
```font``` - (font) font, default: ```-1``` (no font set)  
```text``` - (string) set text, default: ```""``` (no text)  
```letter_case``` - (GMTF enum) transform every character to upper or lower case, default: ```GMTF.DEFAULT```  
```min_chw``` - (real) minimal width of each character, default: ```0``` (WARNING: values other than ```0``` will make the text render character by character instead of line by line)  
```stoppers``` - (string) characters which stop the cursor while moving using ctrl, default: ```" .,()[]{}<>?|:\\+-*/=" + chr(29)```  
#### Colors
```c_bkg_unfocused``` - (struct) unfocused background color and alpha, default: ```{ c: c_gray, a: 1 }```  
```c_bkg_focused``` - (struct) focused background color and alpha, default: ```{ c: c_ltgray, a: 1 }```  
```c_text_unfocused``` - (struct) unfocused text color and alpha, default: ```{ c: c_black, a: 1 }```  
```c_text_focused``` - (struct) focused text color and alpha, default: ```{ c: c_black, a: 1 }```  
```c_selection``` - (struct) mouse selection color and alpha, default: ```{ c: c_blue, a: 0.275 }```  
  
Style can be changed later by calling ```tf1.set_style(<style_struct>)```  
WARNING: Do not run style changes (except colors) every step since it has to update every single character and line which will cause lag  
 
### Text field switching
```tf1.set_next(tf2);```  
```tf2.set_next(tf3);```  
```tf3.set_next(tf1);```  
```tf1.set_previous(tf3);```  
```tf3.set_previous(tf2);```  
```tf2.set_previous(tf1);```  
  
After these are set you can switch text fields using Tab (next) and Shift+Tab (previous)  
  
### Get/Set text
```<text_field_variable>.get_text(keep_enters=false);```  
keep_enters:  
false (default): replace enter characters chr(29) with regular ```\n``` characters  
true: keep original enter characters chr(29), useful when copying between text fields  
  
```<text_field_variable>.set_text(text);```  
Replace whatever is inside with a new text  
