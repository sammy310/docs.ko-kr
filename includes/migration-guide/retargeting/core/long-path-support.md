---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614710"
---
### <a name="long-path-support"></a><span data-ttu-id="d7211-101">긴 경로 지원</span><span class="sxs-lookup"><span data-stu-id="d7211-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="d7211-102">설명</span><span class="sxs-lookup"><span data-stu-id="d7211-102">Details</span></span>

<span data-ttu-id="d7211-103">.NET Framework 4.6.2를 대상으로 하는 앱부터 긴 경로(최대 32K자)가 지원되고 260자(또는 `MAX_PATH`)의 경로 길이 제한이 제거되었습니다. .NET Framework 4.6.2를 대상으로 다시 컴파일된 앱의 경우, 이전에는 260자를 초과했기 때문에 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw했던 코드 경로는 이제 다음 조건에서만 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d7211-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="d7211-104">경로의 길이가 <xref:System.Int16.MaxValue>(32,767)자보다 긴 경우</span><span class="sxs-lookup"><span data-stu-id="d7211-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="d7211-105">운영 체제가 `COR_E_PATHTOOLONG` 또는 동급을 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="d7211-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="d7211-106">.NET Framework 4.6.1 이하 버전을 대상으로 하는 앱의 경우, 경로가 260자를 초과할 때마다 런타임에서 자동으로 <xref:System.IO.PathTooLongException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d7211-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7211-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d7211-107">Suggestion</span></span>

<span data-ttu-id="d7211-108">.NET Framework 4.6.2를 대상으로 하는 앱의 경우, 필요하지 않으면 `app.config` 파일의 `<runtime>` 섹션에 다음을 추가하여 긴 경로 지원을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7211-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="d7211-109">이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱의 경우 `app.config` 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 긴 경로 지원을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7211-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="d7211-110">이름</span><span class="sxs-lookup"><span data-stu-id="d7211-110">Name</span></span>    | <span data-ttu-id="d7211-111">값</span><span class="sxs-lookup"><span data-stu-id="d7211-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7211-112">Scope</span><span class="sxs-lookup"><span data-stu-id="d7211-112">Scope</span></span>   | <span data-ttu-id="d7211-113">부</span><span class="sxs-lookup"><span data-stu-id="d7211-113">Minor</span></span>       |
| <span data-ttu-id="d7211-114">버전</span><span class="sxs-lookup"><span data-stu-id="d7211-114">Version</span></span> | <span data-ttu-id="d7211-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d7211-115">4.6.2</span></span>       |
| <span data-ttu-id="d7211-116">형식</span><span class="sxs-lookup"><span data-stu-id="d7211-116">Type</span></span>    | <span data-ttu-id="d7211-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="d7211-117">Retargeting</span></span> |
