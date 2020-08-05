# Android-Boilerplates



### For resource and service access permissions
```
@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);

    if (requestCode == CAMERA_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Camera Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Camera Permission Denied", Toast.LENGTH_SHORT).show();
        }
    } else if (requestCode == READ_STORAGE_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Read Storage Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Read Storage Permission Denied", Toast.LENGTH_SHORT).show();
        }

    } else if (requestCode == WRITE_STORAGE_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Write Storage Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Write Storage Permission Denied", Toast.LENGTH_SHORT).show();
        }

    }else if (requestCode == READ_CONTACTS_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Read Contacts Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Read Contacts Permission Denied", Toast.LENGTH_SHORT).show();
        }

    }else if (requestCode == WRITE_CONTACTS_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Write Contacts Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Write Contacts Permission Denied", Toast.LENGTH_SHORT).show();
        }

    }else if (requestCode == INTERNET_PERMISSION_CODE) {
        if (
                grantResults.length > 0 &&
                        grantResults[0] == PackageManager.PERMISSION_GRANTED
        ) {
//                Toast.makeText(MainActivity.this, "Internet Permission Granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(getApplicationContext(), "Internet Permission Denied", Toast.LENGTH_SHORT).show();
        }

    }
}
```

```
public static void checkPermission(String permission, int requestCode, Context context) {
    /***************************             To be called this way
     checkPermission(Manifest.permission.WRITE_EXTERNAL_STORAGE, STORAGE_PERMISSION_CODE);
     ************************* */
    if (ContextCompat.checkSelfPermission(
            context, permission) == PackageManager.PERMISSION_DENIED
    ) {
        ActivityCompat.requestPermissions(
                (Activity) context,
                new String[] {permission},
                requestCode
        );
    } else {
//            Toast.makeText(MainActivity.this,"Permission already granted", Toast.LENGTH_SHORT).show();
    }
}
```
