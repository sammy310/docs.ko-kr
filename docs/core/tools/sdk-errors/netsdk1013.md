---
title: 'NETSDK1013: TargetFramework 값을 인식할 수 없습니다.'
description: 유효한 TargetFramework 값을 확인하고 설정하는 방법
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: bcaed878b663f8bc957e8469ffd78caa9babf710
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445699"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: TargetFramework 값을 인식할 수 없음

**이 문서의 적용 대상:** ✔️ .NET 3.1.100 SDK 이상 버전

SDK는 `<TargetFramework>` 또는 `<TargetFrameworks>`의 프로젝트 파일에 제공된 값을 잘 알려진 값으로 구문 분석하려고 합니다.  값을 인식할 수 없는 경우 `TargetFrameworkIdentifier` 또는 `TargetFrameworkVersion` 값을 빈 문자열이나 `Unsupported`로 설정할 수 있습니다.

이 문제를 해결하려면 [지원되는 프레임워크](../../../standard/frameworks.md) 목록에서 `TargetFramework` 값의 철자를 확인하세요.
프로젝트 파일에서 직접 `TargetFrameworkIdentifier` 및 `TargetFrameworkVersion` 속성을 설정할 수도 있습니다.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
