---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614635"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="65f9a-101">URI에서 유니코드 양방향 컨트롤 문자 허용</span><span class="sxs-lookup"><span data-stu-id="65f9a-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="65f9a-102">설명</span><span class="sxs-lookup"><span data-stu-id="65f9a-102">Details</span></span>

<span data-ttu-id="65f9a-103">유니코드는 텍스트의 방향을 지정하는 데 사용되는 몇 가지 특수 컨트롤 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="65f9a-104">이전 버전의 .NET Framework에서 이러한 문자는 백분율로 인코딩된 형식으로 존재했더라도 모든 URI에서 올바르지 않게 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="65f9a-105">[RFC 3987](https://tools.ietf.org/html/rfc3987)을 더 잘 따르기 위해 이제 URI에서 이러한 문자를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="65f9a-106">URI에서 인코딩되지 않은 것을 발견한 경우 백분율로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="65f9a-107">백분율로 인코딩된 것을 발견한 경우 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65f9a-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="65f9a-108">Suggestion</span></span>

<span data-ttu-id="65f9a-109">4\.7.2 이상의 .NET Framework 버전을 대상으로 하는 애플리케이션의 경우 유니코드 양방향 문자에 대한 지원이 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="65f9a-110">이 변경을 원치 않는 경우 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="65f9a-111">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2 이상 버전에서 실행되는 애플리케이션의 경우 유니코드 양방향 문자에 대한 지원이 기본적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="65f9a-112">다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f9a-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="65f9a-113">이름</span><span class="sxs-lookup"><span data-stu-id="65f9a-113">Name</span></span>    | <span data-ttu-id="65f9a-114">값</span><span class="sxs-lookup"><span data-stu-id="65f9a-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65f9a-115">Scope</span><span class="sxs-lookup"><span data-stu-id="65f9a-115">Scope</span></span>   | <span data-ttu-id="65f9a-116">부</span><span class="sxs-lookup"><span data-stu-id="65f9a-116">Minor</span></span>       |
| <span data-ttu-id="65f9a-117">버전</span><span class="sxs-lookup"><span data-stu-id="65f9a-117">Version</span></span> | <span data-ttu-id="65f9a-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="65f9a-118">4.7.2</span></span>       |
| <span data-ttu-id="65f9a-119">형식</span><span class="sxs-lookup"><span data-stu-id="65f9a-119">Type</span></span>    | <span data-ttu-id="65f9a-120">대상 변경</span><span class="sxs-lookup"><span data-stu-id="65f9a-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="65f9a-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="65f9a-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
