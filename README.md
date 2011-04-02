Bitcoin patched branch
======================

This includes various third party branches which might not be of
enough use to the average person to make it into mainline, or might
just be of "beta" status.

This version is built with USE_UPNP=1, making UPnP on by default.

Patches
=======

jgarzik's Patches
-----------------
xlisttransactions
    Adds "xlisttransactions" RPC call.  This lists all wallet transactions, using logic similar to the GUI's display code.

getblockbycount
    Adds "getblockbycount" RPC call.  This dumps the block on the main chain at the specified height, in its entirety.  All data fields, including all transactions, are dumped in a single JSON response.

dumpblock
    A clone of "getblockbycount" RPC call.  Same behavior as "getblockbycount" -- dumps block at specified height.  Adds a "_fulldump" boolean to the output, indicating whether or not the entire block is present on disk (preparing for lightweight block chain support), hoping to address some objections of satoshi.

settxfee
    Add "settxfee" RPC call.  This permits changing of the 'paytxfee' variable at runtime.

print POW failures
    Print a response for every work solution submitted to bitcoind.  Since we already logged successful proof-of-work solutions, the only thing remaining was to log when a proof-of-work check failed, which this patch does.

Gavin Andresen's Patches
------------------------
Port Option
    Adds the -port option to change the listening port.  Also remove the 2h limit on nodes which do not use the default port.

Sipa's Patches
--------------
Spent Per Tx Out
    This patch changes some internal structures to keep track of spentness of each wallet transaction output separately, to support partially-spent transactions.

My Patches (BlueMatt)
---------------------
UPnP
    Adds UPnP support including a WXUI option to disable/enable it at runtime.
