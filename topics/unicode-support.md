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
</dl>

<table>
  <thead>
    <td>Language</td>
    <td>Identifiers</td>
  </thead>
<tbody>
<tr>
  <td>Haskell</td>
  <td><a href="https://www.haskell.org/onlinereport/haskell2010/haskellch2.html#x7-180002.4">✓ <code>Ll|Lu|Lt (Ll|Lu|Lt|Nd|'_'|''')*</code></a></td>
</tr>
<tr>
  <td>Java</td>
  <td><a href="https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isJavaIdentifierStart(int)">✓ <code>L|Nl|Sc|Pc (L|Sc|Pc|Nd|Nl|Mn|Mc|Cf|Cc)*</code></a></td>
</tr>
<tr>
  <td>Python 3</td>
  <td><a href="https://docs.python.org/3/reference/lexical_analysis.html#identifiers">💯 <code>XID_Start XID_Continue*</code></a></td>
</tr>
</trow>
</tbody>
</table>