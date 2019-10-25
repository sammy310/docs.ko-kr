---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522677"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="8a780-101">ID: AddDefaultUI 메서드 오버로드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8a780-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="8a780-102">ASP.NET Core 3.0부터는 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> 메서드 오버로드가 더 이상 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a780-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a780-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8a780-103">Version introduced</span></span>

<span data-ttu-id="8a780-104">3.0</span><span class="sxs-lookup"><span data-stu-id="8a780-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8a780-105">변경 이유</span><span class="sxs-lookup"><span data-stu-id="8a780-105">Reason for change</span></span>

<span data-ttu-id="8a780-106">이 변경 내용은 정적 웹 자산 기능을 채택한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="8a780-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a780-107">권장 작업</span><span class="sxs-lookup"><span data-stu-id="8a780-107">Recommended action</span></span>

<span data-ttu-id="8a780-108">오버로드 대신 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8a780-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="8a780-109">부트스트랩 3을 사용하는 경우 프로젝트 파일의 `<PropertyGroup>` 요소에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8a780-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="8a780-110">범주</span><span class="sxs-lookup"><span data-stu-id="8a780-110">Category</span></span>

<span data-ttu-id="8a780-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8a780-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a780-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8a780-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
