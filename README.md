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
fs.writeFileSync("index.d.ts",dts[0],'utf8');
```
### Why did I create this package 为什么我要创建这个模块
https://github.com/timocov/dts-bundle-generator/issues/137  
Because my project needs to use dynamic TS compilation configuration, the method recommended by the original author can not meet my needs, so I released this package.  
因为我的项目需要使用动态的TS编译配置，原作者推荐的方式无法满足我的需求，因此我发布了这个包。