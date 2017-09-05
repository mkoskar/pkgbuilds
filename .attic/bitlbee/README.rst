bitlbee-mkoskar
===============

:Description: Brings instant messaging (XMPP, MSN, Yahoo!, AIM, ICQ, Twitter) to IRC (mkoskar's patchset)

Contents:

* BitlBee 3.2.2
* ``libevent`` as event handler
* ``skype-displayname.patch``
* ``twitter-account-tag-as-name.patch``


skype-displayname.patch
-----------------------

:Ticket: http://bugs.bitlbee.org/bitlbee/ticket/1169

::

    Subject: [PATCH] Skype display name support
    Maintainer: Miroslav Koškár <http://mkoskar.com/>
    Version: v1

    This is a patch for bitlbee-3.2.2 and its skype protocol:

    * read DISPLAYNAME which corresponds to the name attached to skype contact
      manually through skype client
    * display name is available through ``info`` command
    * display name (if specified) takes precedence over full name so
      ``nick_format = %full_name`` returns display name with full name as a fallback
    * fix bug which caused only offline contacts to receive correct
      ``%full_name``-based nick names


twitter-account-tag-as-name.patch
---------------------------------

:Ticket: http://bugs.bitlbee.org/bitlbee/ticket/1173

::

    Subject: [PATCH] Use Twitter account tag as nick and channel name
    Maintainer: Miroslav Koškár <http://mkoskar.com/>
    Version: v1

    This is a patch for bitlbee-3.2.2 and its twitter protocol:

    * twitter account is accessible now either under <account_tag> nickname
      or through #<account_tag> channel
    * in contrast to status quo (twitter_<handle> / #twitter_<handle>) it
      enables user to have a consistent namings, configurable by setting
      particular twitter account's tag
