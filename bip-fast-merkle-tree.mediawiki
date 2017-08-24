<pre>
  BIP: ???
  Layer: Consensus (soft fork)
  Title: Fast Merkle Trees (Consensus layer)
  Author: Mark Friedenbach <mark@friedenbach.org>
  Status: Draft
  Type: Standards Track
  Created: 2017-08-24
  License: BSD-2-Clause
           OPL
</pre>

==Abstract==

In many applications it is useful to prove membership of a data element in a set without having to reveal the entire contents of that set.
The Merkle hash tree, where inner/non-leaf nodes are labelled with the hash of the labels or values of its children, is a cryptographic tool that achieves this goal.
Bitcoin uses a Merkle hash tree construct for committing the transactions of a block into the block header.
This particular design, created by Satoshi, suffers from a serious flaw related to duplicate entries documented in the National Vulnerability Database as CVE-2012-2459[1], and also suffers from less than optimal performance due to unnecessary double-hashing.

This Bitcoin Improvement Proposal describes a more efficient Merkle hash tree construct that is not vulnerable to CVE-2012-2459 and achieves an approximate 3x decrease in hash tree construction and validation times.

==References==

[1] [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-2459 CVE-2012-2459]
