<h1><b>S3:</b> <i>Simple Storage Service</i></h1>  

The <i>characteristics</i> of an <b>Object</b>  
<ol>
  <li>Key
    <ol>
      <li>Name assigned to the object.</li>
      <li>We use the <b>object key</b> to retrieve the object.</li>
      <li>Key value includes the full path relative to the bucket root.</li>
    </ol>
  </li>
  <li>Version ID
    <ol>
      <li>A <i>key</i> and a <b>Version ID</b> uniquely identify an Object.
    </ol>
  </li>
  <li>Value
  <ol>
    <li>It is the actual content that we store.</li>
    <li>Object values are <b>immutable</b>, which means that after we upload an object, we cannot modify the value.</li>
    <li>If you want to modify the object, you must make a change outside of Amazon S3 and then <b>reupload</b> the object</li>
  </ol>
  </li>
  <li>MetaData
    <ol>
      <li>It is a set of <b>name-value</b> pairs that we can use to store <i>information</i> about the <b>object</b>.
      <li>
    </ol>
  </li>
  <li>Sub-Resources
    <ol>
      <li>To store <i>additional</i> <b>object-specific information</b>.
    </ol>
  </li>
</ol>
