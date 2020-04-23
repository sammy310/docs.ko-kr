---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637199"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="77240-101">ID: AddDefaultUI 메서드 오버로드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="77240-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="77240-102">ASP.NET Core 3.0부터는 [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) 메서드 오버로드가 더 이상 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77240-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77240-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="77240-103">Version introduced</span></span>

<span data-ttu-id="77240-104">3.0</span><span class="sxs-lookup"><span data-stu-id="77240-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="77240-105">변경 이유</span><span class="sxs-lookup"><span data-stu-id="77240-105">Reason for change</span></span>

<span data-ttu-id="77240-106">이 변경 내용은 정적 웹 자산 기능을 채택한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="77240-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77240-107">권장 조치</span><span class="sxs-lookup"><span data-stu-id="77240-107">Recommended action</span></span>

<span data-ttu-id="77240-108">두 개의 인수를 사용하는 오버로드 대신 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="77240-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="77240-109">부트스트랩 3을 사용하는 경우 프로젝트 파일의 `<PropertyGroup>` 요소에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77240-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="77240-110">범주</span><span class="sxs-lookup"><span data-stu-id="77240-110">Category</span></span>

<span data-ttu-id="77240-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77240-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77240-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="77240-112">Affected APIs</span></span>

[<span data-ttu-id="77240-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="77240-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
