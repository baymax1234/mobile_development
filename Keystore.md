### Get Keystore credential

SHA-1 Key for Firebase, Google Map API:

>keytool -list -v -keystore {keystore_name} -alias {alias_name}

Hash Key for Facebook SDK:

```sh
PackageInfo info;
try {
    info = getPackageManager().getPackageInfo("com.you.name", PackageManager.GET_SIGNATURES);
    for (Signature signature : info.signatures) {
        MessageDigest md;
        md = MessageDigest.getInstance("SHA");
        md.update(signature.toByteArray());
        String something = new String(Base64.encode(md.digest(), 0));
        //String something = new String(Base64.encodeBytes(md.digest()));
        Log.e("hash key", something);
    }
} catch (NameNotFoundException e1) {
    Log.e("name not found", e1.toString());
} catch (NoSuchAlgorithmException e) {
    Log.e("no such an algorithm", e.toString());
} catch (Exception e) {
    Log.e("exception", e.toString());
}
```

Or

>http://tomeko.net/online_tools/hex_to_base64.php
