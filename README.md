A sample project to implement CI/CD [Codemagic].

Links to refer 

https://medium.com/hackernoon/top-ci-cd-tools-for-your-android-and-ios-projects-8d356b983b3b - medium link to refer for more CI/CD tools.
https://docs.codemagic.io/getting-started/about-codemagic/ - Info on what is codemagic.
https://docs.codemagic.io/yaml-quick-start/building-a-native-android-app/ - How to implement codemagic in android native apps.

Create a repo in any one of the platform github/bitbucket etc 

1. Create a codemagic.yaml file at the root of the project.
2. Create worflows in the codemagic.yaml file.
3. Create a signing keystore refrence by using following command
4. Command : keytool -genkey -v -keystore codemagic.keystore -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias codemagic [This generates the keystore file]
5. If you encounter a warming [The JKS keystore uses a proprietary format. It is recommended to migrate to PKCS12 which is an industry standard format using "keytool -importkeystore -srckeystore codemagic_test.keystore -destkeystore codemagic_test.keystore -deststoretype pkcs12".] then execute the same command again to generate keystore.
6. Generated keystore must be uploaded on Codemagic portal in your repo settings you'll find "Code signing identities". [link to upload keystore file - https://www.youtube.com/watch?v=wPpGTY6Sis0]
7. Update your build.gradle file with signingConfigs.
8. Make sure the dependency and target sdk are uptodate[ might throw an error when building apk via Codemagic portal].
9. Push all the changes to your repo.
10. Go to Codemagic -> click on apps & your codemagic.yaml will be automatically loaded or select the branch it will appear.
11. Click  on start new build and select your workflows the builds will be generated within 5-10 minutes.
