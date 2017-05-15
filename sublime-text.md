# List packages of Sublime Text

* Emmet
* Materialize
* Therm
* Autofilename
* SidebarEnchacements
* BracketHighlight  

## Settings 
```json
{
	"bold_folder_labels": true,
	"color_scheme": "Packages/Jeffrey Way Theme/schemes/Facebook.tmTheme",
	"drag_text": false,
	"font_size": 12,
	"ignored_packages":
	[
		"Vintage"
	],
	"line_padding_bottom": 6,
	"line_padding_top": 6,
	"overlay_scroll_bars": "enabled",
	"theme": "Material Facebook.sublime-theme",
	"word_wrap": "true"
}



```

## Keybindigs
```json
[
	{ "keys": ["ctrl+alt+f"], "command": "reindent" , "args": {"single_line": false} },
	{ "keys": ["ctrl+}"], "command": "toggle_comment", "args": { "block": false } },
	{ "keys": ["ctrl+{"], "command": "toggle_comment", "args": { "block": true } },  
	{ 
		"keys": ["tab"], "command": "expand_abbreviation_by_tab", 
		"context":
	    	[
		        { "operand": "source.js", "operator": "equal", "match_all": true, "key": "selector" },
		        { "match_all": true, "key": "selection_empty" },
		        { "operator": "equal", "operand": false, "match_all": true, "key": "has_next_field" },
		        { "operand": false, "operator": "equal", "match_all": true, "key": "auto_complete_visible" },
		        { "match_all": true, "key": "is_abbreviation" }
	    	]
	}
]

```

