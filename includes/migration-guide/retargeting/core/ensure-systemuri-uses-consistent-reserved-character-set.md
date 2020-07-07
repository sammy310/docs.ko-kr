---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614662"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="29035-101">System.Uri가 일관된 예약된 문자 집합을 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29035-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="29035-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="29035-102">Details</span></span>

<span data-ttu-id="29035-103"><xref:System.Uri?displayProperty=fullName>에서 때로는 디코딩되는 특정 백분율로 인코딩된 문자는 이제 일관되게 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="29035-104">이는 URI의 경로, 쿼리, 조각 또는 사용자 정보 구성 요소에 액세스하는 속성 및 메서드에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="29035-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="29035-105">이 동작은 다음 두 항목 모두가 true인 경우에만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="29035-106">URI는 다음 예약된 문자의 인코딩된 형식을 포함합니다. `:`, `'`, `(`, `)`, `!` 또는 `*`</span><span class="sxs-lookup"><span data-stu-id="29035-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="29035-107">URI는 유니코드 또는 인코딩된 예약되지 않은 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="29035-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="29035-108">위의 두 항목 모두가 true인 경우 인코딩된 예약된 문자는 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="29035-109">이전 버전의 .NET Framework에서는 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="29035-110">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="29035-110">Suggestion</span></span>

<span data-ttu-id="29035-111">4\.7.2 이상의 .NET Framework 버전을 대상으로 하는 애플리케이션의 경우 새로운 디코딩 동작이 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="29035-112">이 변경을 원치 않는 경우 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29035-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="29035-113">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2 이상 버전에서 실행되는 애플리케이션의 경우 새로운 디코딩 동작이 기본적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="29035-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="29035-114">다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29035-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="29035-115">이름</span><span class="sxs-lookup"><span data-stu-id="29035-115">Name</span></span>    | <span data-ttu-id="29035-116">값</span><span class="sxs-lookup"><span data-stu-id="29035-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="29035-117">Scope</span><span class="sxs-lookup"><span data-stu-id="29035-117">Scope</span></span>   | <span data-ttu-id="29035-118">부</span><span class="sxs-lookup"><span data-stu-id="29035-118">Minor</span></span>       |
| <span data-ttu-id="29035-119">버전</span><span class="sxs-lookup"><span data-stu-id="29035-119">Version</span></span> | <span data-ttu-id="29035-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="29035-120">4.7.2</span></span>       |
| <span data-ttu-id="29035-121">형식</span><span class="sxs-lookup"><span data-stu-id="29035-121">Type</span></span>    | <span data-ttu-id="29035-122">대상 변경</span><span class="sxs-lookup"><span data-stu-id="29035-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="29035-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="29035-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
