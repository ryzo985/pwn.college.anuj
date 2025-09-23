# An epic filesystem quest

Using primarily ``cd``, ``cat``, and ``ls``, we were told to follow clues to find the flag. The first clue was said to be in */* and that we had to cat the clue file (not actually named "clue" but something along those lines) in */* to begin.

## My solve
**Flag: 'pwn.college{oVHGjYvdvqmPybPSLQ_kYNC3uzf.QX5IDO0wyN4ETMzEzW}'**

Following the instructions, i ran ``cd /`` and then ran ``ls`` to view the files in */*, I then spotted the "DISPATCH" file, which stood out. Upon running ``cat DISPATCH``, I was told the next clue is in */usr/lib/python3/dist-packages/pyasn1/codec/cer*. 

After running ``cd /usr/lib/python3/dist-packages/pyasn1/codec/cer``, and then ``ls`` to view the files in this directory, I spotted the "BRIEF" file, which upon ``cat``ing, told us that the next clue lies in */usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util* and is **hidden**, which means it is a dot-prepended file. 
After running ``cd /usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util``, I ran ``ls -a`` to list all the files, including the dot-prepended hidden files. Here I found a file named ".SECRET", which once ``cat``ted told us that the next clue was in */usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold*. 
Next, I ran ``cd /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold`` and then ``ls`` to view the files. Only 2 files were here, one of which was named "CLUE". ``cat``ing this file told me that the next clue was */usr/lib/ruby/2.7.0/rdoc/markup*.
I ran ``cd /usr/lib/ruby/2.7.0/rdoc/markup`` and then ``ls``, after which I spotted a file named TRACE. Running ``cat TRACE`` told me that the next clue was in */usr/lib/debug/.build-id/b5* and that it was **delayed**, which means that it will not become readable until you enter the directory with ``cd``. Which is fine because I've been entering all the directories with ``cd`` anyway.
So, I ran ``cd /usr/lib/debug/.build-id/b5``, and then ``ls``, where we find the "TIP" file. Running ``cat TIP`` tells us that the next clue lies within the */usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__* directory. 
I used ``cd /usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__`` to enter the directory, and then ran ``ls`` to list the files present, where I found the "LEAD" file. Using ``cat`` on the "LEAD" file tells me the next clue is in */usr/lib/ruby/2.7.0/bundler/templates*, and that it's **delayed**.
I ran ``cd /usr/lib/ruby/2.7.0/bundler/templates``, and then ``ls``, to find the "BLUEPRINT" file. Reading this file with ``cat`` tells me the next clue is in */opt/linux/linux-5.4/Documentation/features/debug/kgdb* and that it's **trapped**, which means we'll have to read it without ``cd``ing into the directory, or else the file will self-destruct. 
So to avoid having the file self-destruct, i just run ``ls /opt/linux/linux-5.4/Documentation/features/debug/kgdb`` without ``cd``ing anywhere. I see the "NUGGET-TRAPPED" file. After running ``cat /opt/linux/linux-5.4/Documentation/features/debug/kgdb/NUGGET-TRAPPED``, it returned the flag and the challenge was complete.

```bash
Connected!
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
DISPATCH  challenge  flag  lib32   media  opt   run   sys  var
bin       dev        home  lib64   mnt    proc  sbin  tmp
boot      etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ cat DISPATCH
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/pyasn1/codec/cer
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/python3/dist-packages/pyasn1/codec/cer
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pyasn1/codec/cer$ ls
BRIEF  __init__.py  __pycache__  decoder.py  encoder.py
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pyasn1/codec/cer$ cat BRIEF
Congratulations, you found the clue!
The next clue is in: /usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/pyasn1/codec/cer$ cd /usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util$ ls -a
.   .SECRET             method-owner-finder.rb  output.rb
..  backtracefilter.rb  observable.rb           procwrapper.rb
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util$ cat .SECRET
Great sleuthing!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold
hacker@commands~an-epic-filesystem-quest:/usr/share/rubygems-integration/all/gems/test-unit-3.3.5/lib/test/unit/util$ cd /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ ls -a
.  ..  CLUE  Main.js
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ cat CLUE
Tubular find!
The next clue is in: /usr/lib/ruby/2.7.0/rdoc/markup
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/STIX-Web/Latin/Bold$ cd /usr/lib/ruby/2.7.0/rdoc/markup
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/rdoc/markup$ ls -a
.                     heading.rb             to_bs.rb
..                    include.rb             to_html.rb
TRACE                 indented_paragraph.rb  to_html_crossref.rb
attr_changer.rb       list.rb                to_html_snippet.rb
attr_span.rb          list_item.rb           to_joined_paragraph.rb
attribute_manager.rb  paragraph.rb           to_label.rb
attributes.rb         parser.rb              to_markdown.rb
blank_line.rb         pre_process.rb         to_rdoc.rb
block_quote.rb        raw.rb                 to_table_of_contents.rb
document.rb           regexp_handling.rb     to_test.rb
formatter.rb          rule.rb                to_tt_only.rb
hard_break.rb         to_ansi.rb             verbatim.rb
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/rdoc/markup$ cat TRACE
Great sleuthing!
The next clue is in: /usr/lib/debug/.build-id/b5

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/rdoc/markup$ cd /usr/lib/debug/.build-id/b5
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/b5$ ls
90fc8e2afe393bc8ee4052de3a6de82c601f23.debug  TIP
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/b5$ cat TIP
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/b5$ cd /usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__$ ls
LEAD  __init__.cpython-38.pyc  all.cpython-38.pyc  huffman.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__$ cat LEAD
Congratulations, you found the clue!
The next clue is in: /usr/lib/ruby/2.7.0/bundler/templates

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sage/coding/source_coding/__pycache__$ cd /usr/lib/ruby/2.7.0/bundler/templates
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/bundler/templates$ ls
BLUEPRINT   Executable.bundler     Gemfile  newgem
Executable  Executable.standalone  gems.rb
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/bundler/templates$ cd BLUEPRINT
bash: cd: BLUEPRINT: Not a directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/bundler/templates$ cat BLUEPRINT
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/Documentation/features/debug/kgdb

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/ruby/2.7.0/bundler/templates$ cd
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/linux/linux-5.4/Documentation/features/debug/kgdb
cat: /opt/linux/linux-5.4/Documentation/features/debug/kgdb: Is a directory
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/linux/linux-5.4/Documentation/features/debug/kgdb
NUGGET-TRAPPED  arch-support.txt
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/linux/linux-5.4/Documentation/features/debug/kgdb/NUGGET-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{oVHGjYvdvqmPybPSLQ_kYNC3uzf.QX5IDO0wyN4ETMzEzW}
```

## What I learned
I gained extensive practice with using ``cat``, ``ls``, and ``cd``. I learnt about "delayed" and "trapped" files, but I am not so sure how relevant these are when it comes to real usage.