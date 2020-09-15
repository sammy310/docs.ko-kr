---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614792"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="79e5d-101">DataContractJsonSerializer를 사용한 제어 문자의 serialization가 이제 ECMAScript V6 및 V8과 호환됨</span><span class="sxs-lookup"><span data-stu-id="79e5d-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="79e5d-102">설명</span><span class="sxs-lookup"><span data-stu-id="79e5d-102">Details</span></span>

<span data-ttu-id="79e5d-103">.NET Framework 4.6.2 이하 버전에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName>이 ECMAScript V6 및 V8 표준과 호환되는 방식으로 \b, \f, \t 등의 일부 특수 제어 문자를 직렬화하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="79e5d-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="79e5d-104">.NET Framework 4.7부터는 이러한 제어 문자의 직렬화가 ECMAScript V6 및 V8과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="79e5d-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="79e5d-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="79e5d-105">Suggestion</span></span>

<span data-ttu-id="79e5d-106">.NET Framework 4.7을 대상으로 하는 앱의 경우 기본적으로 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e5d-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="79e5d-107">이 동작을 원치 않는 경우 app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79e5d-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="79e5d-108">이름</span><span class="sxs-lookup"><span data-stu-id="79e5d-108">Name</span></span>    | <span data-ttu-id="79e5d-109">값</span><span class="sxs-lookup"><span data-stu-id="79e5d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="79e5d-110">Scope</span><span class="sxs-lookup"><span data-stu-id="79e5d-110">Scope</span></span>   | <span data-ttu-id="79e5d-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="79e5d-111">Edge</span></span>        |
| <span data-ttu-id="79e5d-112">버전</span><span class="sxs-lookup"><span data-stu-id="79e5d-112">Version</span></span> | <span data-ttu-id="79e5d-113">4.7</span><span class="sxs-lookup"><span data-stu-id="79e5d-113">4.7</span></span>         |
| <span data-ttu-id="79e5d-114">형식</span><span class="sxs-lookup"><span data-stu-id="79e5d-114">Type</span></span>    | <span data-ttu-id="79e5d-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="79e5d-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="79e5d-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="79e5d-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
