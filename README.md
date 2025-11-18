diff --git a/README.md b/README.md
new file mode 100644
index 0000000000000000000000000000000000000000..d6ea8eea9c10c0915183274e1d327cf471f8a52f
--- /dev/null
+++ b/README.md
@@ -0,0 +1,23 @@
+# essentialcraft-data
+
+Raw pricing CSV for the Squarespace label quote tool.
+
+## Download URL
+Use this URL in client code so cache-busting parameters work correctly:
+
+```
+https://raw.githubusercontent.com/essentialpack/essentialcraft-data/main/Combined_Label_Pricing.csv?raw=1
+```
+
+The `?raw=1` ensures any additional `&cache=` parameters get treated as querystring values instead of part of the filename, preventing "failed to fetch" errors.
+
+## Cache busting / refresh instructions
+If you update the CSV and want visitors to see the new data immediately, bump the cache-busting querystring:
+
+1. Keep the `?raw=1` suffix.
+2. Append `&cache=` followed by a new value (e.g., a timestamp). Example:
+   - `https://raw.githubusercontent.com/essentialpack/essentialcraft-data/main/Combined_Label_Pricing.csv?raw=1&cache=20240908`
+3. In JavaScript, use something dynamic so you never have to edit HTML manually:
+   - `const url = "https://raw.githubusercontent.com/essentialpack/essentialcraft-data/main/Combined_Label_Pricing.csv?raw=1&cache=" + Date.now();`
+
+No other code changes are required beyond using the `?raw=1` URL and updating the `&cache=` value when you need an immediate refresh.
