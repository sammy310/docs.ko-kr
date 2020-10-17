---
title: 'NETSDK1145: 타기팅 팩 또는 apphost 팩 누락'
description: NuGet 패키지 복원이 지원되지 않는 동안 타기팅 팩 누락 문제를 해결하는 방법
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805311"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: 타기팅 팩 또는 apphost 팩 누락

**이 문서의 적용 대상:** ✔️ .NET 5.0.100 SDK 이상 버전

.NET SDK가 NETSDK1145 오류를 실행하는 경우 타기팅 팩 또는 apphost 팩이 설치되어 있지 않고 NuGet 패키지 복원이 지원되지 않는 것입니다. 이 오류는 일반적으로 C++/CLI용 Visual Studio 프로젝트에 포함된 버전보다 최신 버전의 SDK를 사용하는 경우에 발생합니다. Visual Studio를 업그레이드하고, 특정 SDK 버전을 지정하는 경우 _global.json_을 제거한 다음, 최신 SDK를 제거합니다. 또는 타기팅 버전이나 apphost 버전을 재정의할 수 있습니다. 오류 메시지의 팩 디렉터리에서 프로젝트의 대상 프레임워크와 일치하는 버전을 찾습니다. 프로젝트에 다음 코드를 추가합니다.

apphost 팩의 경우

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

타기팅 팩의 경우

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
