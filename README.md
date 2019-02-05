My fork of mail2taskwarrior.  Originally started because I needed to make it work from postfix's pipe command, but I have some bigger plans for this too.

In my work, I had to setup an alternate email proxy, and used mxguarddog.
[stop spam](http://mxguarddog.com/)

Add a task to taskwarrior via email. Makes use of the taskw Python bindings.

 http://taskwarrior.org
 https://github.com/ralphbean/taskw

For use with procmail or maildrop. Example using maildrop's .mailfilter:


  if ($SIZE < 8192 && /^From:.*myaddress@example.com/ && /^To:.*taskwarrior@/)
  {
    log "add task via mail2taskwarrior"
    xfilter "devel/mail2taskwarrior/mail2taskwarrior"
    exit
  }
