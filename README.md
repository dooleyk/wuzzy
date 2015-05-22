# wuzzy language

Language extension created using...

Project -> New Project from Template and select the Create Komodo Language
 
Did check 'code intelligence facilities' wizard option.

Get langinfo and import errors popping up repeatedly in 9.0 when editing a wuzzy (.wzy) file, though color coding and Edit Preferences Language stuff works. (These same errors also occur in 8.0 though it is less noticable because they only show up in the log, and not in popup boxes.)

[2015-05-22 07:53:31,199] [ERROR] codeintel.citadel: unexpected error scanning `wuzzy.wzy'
Traceback (most recent call last):
  File "/home/dooleyk/Komodo-IDE-9/lib/mozilla/python/komodo/codeintel2/citadel.py", line 264, in scan
    scan_tree = cile_driver.scan_purelang(self)
  File "/home/dooleyk/.komodoide/9.0/XRE/extensions/wuzzy_language@wuzzy.org/pylib/codeintel_wuzzy.py", line 263, in scan_purelang
    import cile_wuzzy
ImportError: No module named cile_wuzzy

[2015-05-22 07:53:31,278] [ERROR] codeintel.langintel: error getting langinfo for 'Wuzzy'
Traceback (most recent call last):
  File "/home/dooleyk/Komodo-IDE-9/lib/mozilla/python/komodo/codeintel2/langintel.py", line 61, in langinfo
    self._langinfo_cache = self.mgr.lidb.langinfo_from_komodo_lang(self.lang)
  File "/home/dooleyk/Komodo-IDE-9/lib/mozilla/python/komodo/langinfo.py", line 311, in langinfo_from_komodo_lang
    raise LangInfoError("no info on %r komodo lang" % komodo_lang)
LangInfoError: no info on 'Wuzzy' komodo lang


I have been able to 'fix' the import error by pasting the cile_wuzzy.py code inside codeintel_wuzzy.py.

