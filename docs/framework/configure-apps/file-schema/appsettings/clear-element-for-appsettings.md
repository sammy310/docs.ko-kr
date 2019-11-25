---
title: <appSettings>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088731"
---
# <a name="clear-element-for-appsettings"></a>\<appSettings에 대 한 \<clear > 요소 >

사용자 지정 응용 프로그램 설정을 지웁니다.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>구문

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>특성

없음

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | 파일 경로, XML Web services Url 또는 기타 사용자 지정 응용 프로그램 구성 정보와 같은 사용자 지정 응용 프로그램 설정을 포함 합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="example"></a>예제

다음 예제에서는 사용자 지정 구성 설정을 지우는 방법을 보여 줍니다.

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>참조

- [.NET Framework에 대 한 구성 파일 스키마](../index.md)
