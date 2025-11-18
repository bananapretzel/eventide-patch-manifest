# 📦 How to Add Patches

1. **Prepare your patch files**  
   Collate the modified **.DAT** files in their original file structure, with the root being the **ROM** folder.
   - Be careful **not to double-nest** the archive. When you open the ZIP, the first folder must be `ROM`.
   - The launcher will merge the patch `ROM` folder with the user's installation `ROM` folder, overwriting `.DAT` files with the same name in their respective sub-folders.

---

2. **Create a new GitHub Release**  
   In the GitHub repo for patches, go to **Releases** and create a new release.  
   Give it a title (usually the patch version).  
   *The release name doesn't matter for the launcher.*

---

3. **Create a version tag**  
   Under **Tag**, select **“Create new tag”** and name it the version of the patch, e.g.: v1.0.3


---

4. **Upload your ZIP**  
Drag and drop the ZIP file or manually select it into the section:

    “Attach binaries by dropping them here or selecting them”

---

5. **Publish the release**

---

6. **Update `patch-manifest.json`**  
In your editor, modify `patch-manifest.json` and add a new patch entry to the `patches` array.  
Fill in the `"from"` and `"to"` keys with their appropriate values, incrementing by `.1`.

Example:

```json
{
  "from": "1.0.2",
  "to": "1.0.3"
}
```
7. **Add the SHA-256 hash and file size**

    If you're using **7-Zip**:

- Right-click the ZIP

- `7-Zip → CRC → SHA-256`

- This shows both the hash and the size in bytes.

8. **Add the download URL**
   
   Right-click the `.zip` in the GitHub release → **Copy link** → paste it into `"fullUrl"`.

9. **Commit and push**
    
   Commit your changes and push the updated manifest.