# Install Package Control  
Ctrl + `  

import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

# Packages to install:
- MarkdownEditing (https://github.com/SublimeText-Markdown/MarkdownEditing#additional-color-themes)
- BracketHighlighter
- Monokai Extended
- Jekyll
- JsFormat (for Javascript)
- Pretty JSON
- HTML-CSS-JS Prettify (https://github.com/victorporof/Sublime-HTMLPrettify)

# Select all instances same text
Ctrl + D or Alt + F3

# Replace All
Ctrl + Alt + Enter

# Change font-size
Preferences/Settings - User
"font_size": 9
"font_face": "Courier New"

# Default word wrap
"word_wrap": true

# Add shortcut to reindent: Preferences - Keybindings - User
[
    { "keys": ["f12"], "command": "reindent", "args": {"single_line": false}} 
]

# Increase font size of sidebar label
# http://stackoverflow.com/questions/18288870/sublime-text-3-how-to-change-the-font-size-of-the-file-sidebar
touch /home/davidheryanto/.config/sublime-text-3/Packages/User/Default.sublime-theme
[
    {
        "class": "sidebar_label",
        "font.bold": false,
        "font.size": 14
    },
    {
		"class": "tab_label",
		"font.size": 12 
    }
]

# Set file to open with syntax
View - Syntax - Open all with current extension as

# Disable update
"update_check": false

# Add windows context menu -- Save as .bat and run as admin
@echo off
SET st2Path=C:\Program Files\Sublime Text 3\sublime_text.exe

rem add it for all file types
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3"         /t REG_SZ /v "" /d "Open with Sublime Text 3"   /f
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3"         /t REG_EXPAND_SZ /v "Icon" /d "%st2Path%,0" /f
@reg add "HKEY_CLASSES_ROOT\*\shell\Open with Sublime Text 3\command" /t REG_SZ /v "" /d "%st2Path% \"%%1\"" /f

rem add it for folders
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3"         /t REG_SZ /v "" /d "Open with Sublime Text 3"   /f
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3"         /t REG_EXPAND_SZ /v "Icon" /d "%st2Path%,0" /f
@reg add "HKEY_CLASSES_ROOT\Folder\shell\Open with Sublime Text 3\command" /t REG_SZ /v "" /d "%st2Path% \"%%1\"" /f
pause

# Nice setting on Fedora
# ======================
# Make sure to have installed Monaco.otf font
{
	"font_face": "Monaco",
	"font_options":
	[
		"subpixel_antialias"
	],
	"font_size": 10
}

# Focus on the sidebar
Ctrl + 0
# Change focus back to editor
Ctrl + 1