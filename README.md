## Forked from timocov/dts-bundle-generator@6.9.0
### Difference from timocov/dts-bundle-generator
Add compilerOptions to override the attribute with the same name under tsconfig.json.So you no longer need to use a separate tsonfig JSON to handle personalized compilation configuration.
### Example
```
let myCompilerOptions={"removeComments": false};
let dts = dtsBundleGenerator.generateDtsBundle([
    {
        "filePath": "./index.ts"
    }
],{
    preferredConfigPath:'tsconfig.json',
    compilerOptions:myCompilerOptions
});
fs.writeFileSync(`${DIST_PATH}/${ENV.dtsBundle.outFile||"index.d.ts"}`,dts[0],'utf8');
```