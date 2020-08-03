---
title: DataContractJsonSerializer로 제어 문자 직렬화
description: 제어 문자 직렬화가 .NET Framework 4.7의 ECMAScript V6 및 V8에 맞게 변경되는 방식에 대해 알아봅니다.
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: a317884da014097a7a60aef2cef4ec146ccb04f7
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475387"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="7426e-103">완화: DataContractJsonSerializer로 제어 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="7426e-103">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="7426e-104">.NET Framework 4.7부터 제어 문자가 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>로 직렬화되는 방식이 ECMAScript V6 및 V8에 맞게 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-104">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span>

## <a name="impact"></a><span data-ttu-id="7426e-105">영향</span><span class="sxs-lookup"><span data-stu-id="7426e-105">Impact</span></span>

<span data-ttu-id="7426e-106">.NET Framework 4.6.2 이하 버전에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>가 ECMAScript V6 및 V8 표준과 호환되는 방식으로 `\b`, `\f`, `\t` 등의 일부 특수 제어 문자를 serialize하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-106">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="7426e-107">.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이러한 제어 문자의 직렬화가 ECMAScript V6 및 V8과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-107">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="7426e-108">다음 API가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-108">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="7426e-109">완화</span><span class="sxs-lookup"><span data-stu-id="7426e-109">Mitigation</span></span>

<span data-ttu-id="7426e-110">.NET Framework 4.7 이상의 .NET Framework 버전을 대상으로 하는 앱의 경우 이 동작이 기본적으로 사용되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-110">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="7426e-111">이 동작을 원치 않는 경우 app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7426e-111">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="7426e-112">참조</span><span class="sxs-lookup"><span data-stu-id="7426e-112">See also</span></span>

- [<span data-ttu-id="7426e-113">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="7426e-113">Application compatibility</span></span>](application-compatibility.md)
