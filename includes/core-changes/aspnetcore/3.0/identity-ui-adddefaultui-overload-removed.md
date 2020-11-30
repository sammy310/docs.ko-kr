---
ms.openlocfilehash: e77312605ee367c159171e305d8f69429f9ac58b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032559"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="abd4f-101">ID: AddDefaultUI 메서드 오버로드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="abd4f-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="abd4f-102">ASP.NET Core 3.0부터는 [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) 메서드 오버로드가 더 이상 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abd4f-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="abd4f-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="abd4f-103">Version introduced</span></span>

<span data-ttu-id="abd4f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="abd4f-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="abd4f-105">변경 이유</span><span class="sxs-lookup"><span data-stu-id="abd4f-105">Reason for change</span></span>

<span data-ttu-id="abd4f-106">이 변경 내용은 정적 웹 자산 기능을 채택한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="abd4f-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="abd4f-107">권장 조치</span><span class="sxs-lookup"><span data-stu-id="abd4f-107">Recommended action</span></span>

<span data-ttu-id="abd4f-108">두 개의 인수를 사용하는 오버로드 대신 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="abd4f-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="abd4f-109">부트스트랩 3을 사용하는 경우 프로젝트 파일의 `<PropertyGroup>` 요소에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="abd4f-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="abd4f-110">범주</span><span class="sxs-lookup"><span data-stu-id="abd4f-110">Category</span></span>

<span data-ttu-id="abd4f-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="abd4f-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="abd4f-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="abd4f-112">Affected APIs</span></span>

[<span data-ttu-id="abd4f-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="abd4f-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
