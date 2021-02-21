
lua builtin modules ported from
https://github.com/EmmyLua/IntelliJ-EmmyLua/tree/master/src/main/resources/std,
to make EmmyLua-LanguageServer work for lua builtin modules


# use in `EmmyLua-LanguageServer`

```
call coc#config('languageserver.EmmyLua', {
        \   'command': &shell,
        \   'args': [&shellcmdflag, 'java -cp EmmyLua-LS-all.jar com.tang.vscode.MainKt'],
        \   'filetypes': ['lua'],
        \   'initializationOptions': {
        \     'stdFolder': 'file:///path_to_this_repo/std/Lua54',
        \   },
        \ })
```

note the `file://` is required to make the `stdFolder` work,
[see also](https://github.com/EmmyLua/EmmyLua-LanguageServer/issues/13),
samples:

* `file:///abs_path`
* `file://../rel_path`
* `file://C:\Windows_path`

