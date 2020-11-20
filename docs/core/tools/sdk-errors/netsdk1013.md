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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="3b3f2-103">NETSDK1013: TargetFramework 값을 인식할 수 없음</span><span class="sxs-lookup"><span data-stu-id="3b3f2-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="3b3f2-104">**이 문서의 적용 대상:** ✔️ .NET 3.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="3b3f2-104">**This article applies to:** ✔️ .NET 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="3b3f2-105">SDK는 `<TargetFramework>` 또는 `<TargetFrameworks>`의 프로젝트 파일에 제공된 값을 잘 알려진 값으로 구문 분석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3f2-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="3b3f2-106">값을 인식할 수 없는 경우 `TargetFrameworkIdentifier` 또는 `TargetFrameworkVersion` 값을 빈 문자열이나 `Unsupported`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b3f2-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="3b3f2-107">이 문제를 해결하려면 [지원되는 프레임워크](../../../standard/frameworks.md) 목록에서 `TargetFramework` 값의 철자를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3b3f2-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="3b3f2-108">프로젝트 파일에서 직접 `TargetFrameworkIdentifier` 및 `TargetFrameworkVersion` 속성을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b3f2-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
