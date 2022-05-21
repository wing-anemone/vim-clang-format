# Clang-format for vim

setting in **.vimrc** : 

```vimrc
"v模式选中部分进行code格式化
vmap <C-k> :py3f your-path/clang-format.py<CR>
 
function! Formatonsave() "保存时全部代码格式化，慎用！
  "let l:formatdiff = 1 "只format修改的部分
  let l:lines = 'all'
  py3f your-path/clang-format.py
endfunction
autocmd BufWritePre *.h,*.cc,*.cpp call Formatonsave()
```



.clang-format was generate by 

```shell
clang-format -style=google -dump-config > .clang-format
```



