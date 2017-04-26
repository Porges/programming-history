## Unicode support

<dl>
<dt>Identifiers</dt>
<dd>
    <ul>
    <li>💯: follows <a href="http://www.unicode.org/reports/tr31/">UAX-31</a>.</li>
    <li>✓: allows Unicode in some form.</li>
    <li>✗: does not allow Unicode.</li>
    </ul>
</dd>
<dt>Char type</dt>
<dd>
    <ul>
    <li>💯: can represent all emoji (e.g. no distinguishing between characters and strings).</li>
    <li>✓: can represent all codepoints.</li>
    <li>✗: cannot represent all codepoints.</li>
    </ul>
</dd>
</dl>

<table>
  <thead>
    <td>Language</td>
    <td>Identifiers</td>
    <td>Char type</td>
  </thead>
<tbody>
<tr>
  <td>C#</td>
  <td><a href="https://msdn.microsoft.com/en-us/library/aa664670(v=vs.71).aspx">✓ <code>L|Nl|'_' (L|Pc|Nd|Nl|Mn|Mc|Cf)*</code></a></td>
  <td>✗ (UTF-16 code unit)</td>
</tr>
<tr>
  <td>Haskell</td>
  <td><a href="https://www.haskell.org/onlinereport/haskell2010/haskellch2.html#x7-180002.4">✓ <code>Ll|Lu|Lt (Ll|Lu|Lt|Nd|'_'|''')*</code></a></td>
  <td><a href="https://www.haskell.org/onlinereport/haskell2010/haskellch2.html#x7-200002.6">✓</a></td>
</tr>
<tr>
  <td>Java</td>
  <td><a href="https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(int)">✓ <code>L|Nl|Sc|Pc (L|Sc|Pc|Nd|Nl|Mn|Mc|Cf|Cc)*</code></a></td>
  <td><a href="https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html">✗ (UTF-16 code unit)</a></td>
</tr>
<tr>
  <td>Python 3</td>
  <td><a href="https://docs.python.org/3/reference/lexical_analysis.html#identifiers">💯 <code>XID_Start XID_Continue*</code></a></td>
  <td><a href="https://docs.python.org/3/reference/lexical_analysis.html#string-and-bytes-literals">💯</a></td>
</tr>
<tr>
  <td>Swift</td>
  <td><a href="https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/LexicalStructure.html#//apple_ref/doc/uid/TP40014097-CH30-ID410">✓ (see link)</a></td>
  <td><a href="https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/StringsAndCharacters.html">✓ (can represent extended grapheme clusters as well)</a></td>
</tr>
</tbody>
</table>