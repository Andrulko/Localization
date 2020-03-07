---
title: صفحة بلا عنوان
description: مساعد صغير في TypeScript
published: true
date: 2020-01-19T23:42:36.260Z
tags:
---

# إعدادات TypeScript

## مقدمة

عندما تقوم بتنزيل و تفك الضغط على مساحة العمل ، سترى ملف يسمى `tsconfig. s` في الروت ومجلدات presence، يستخدم هذا الملف لإعداد **محول برمجيTypeScript**. لقد تم تكوينه من أجلك، لذا لا تقلق حيال ذلك.

نحن نريد فقط وصف بعض الإعدادات التي يجب أن تعرفها.

## اعدادات الروت

في ملف إعدادات الروت سترى شيئا كهذا.

```javascript
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es6",
    "removeComments": true
  },
  "exclude": ["node_modules"]
}
```

| Property            | الوصف                                                                                           |
|:------------------- |:----------------------------------------------------------------------------------------------- |
| **compilerOptions** | تستخدم لإعداد المحول برمجي، معظم الخصائص موجودة هنا.                                            |
| module              | You can read more about that [here](https://www.typescriptlang.org/docs/handbook/modules.html). |
| target              | Defines the JavaScript version you are compiling.                                               |
| removeComments      | Removing comments from compiled files.                                                          |
| **exclude**         | Here you can define the folders that you want to exclude from the future compilation.           |

## Presence Configuration

```javascript
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
}
```

| Property            | الوصف                                                                                  |
|:------------------- |:-------------------------------------------------------------------------------------- |
| **extends**         | Used for extending the base `tsconfig` file for various tasks.                         |
| **compilerOptions** | See [**Root Configuration**](/dev/presence/tsconfig#root-configuration) for more info. |
| outDir              | Defines the output directory for compiled files.                                       |