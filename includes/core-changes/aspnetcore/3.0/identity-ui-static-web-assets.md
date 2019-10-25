---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394067"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="ba9b3-101">ID: UI는 정적 웹 자산 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="ba9b3-102">ASP.NET Core 3.0에는 정적 웹 자산 기능이 도입되었으며 ID UI에서 이를 채택했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ba9b3-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="ba9b3-103">Change description</span></span>

<span data-ttu-id="ba9b3-104">ID UI가 정적 웹 자산 기능을 채택한 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="ba9b3-105">프레임워크 선택은 프로젝트 파일에서 `IdentityUIFrameworkVersion` 속성을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="ba9b3-106">부트스트랩 4는 ID UI의 기본 UI 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="ba9b3-107">부트스트랩 3은 수명이 다되었으므로 지원되는 버전으로 마이그레이션하는 것을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ba9b3-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ba9b3-108">Version introduced</span></span>

<span data-ttu-id="ba9b3-109">3.0</span><span class="sxs-lookup"><span data-stu-id="ba9b3-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ba9b3-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ba9b3-110">Old behavior</span></span>

<span data-ttu-id="ba9b3-111">ID UI의 기본 UI 프레임워크는 **부트스트랩 3**입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="ba9b3-112">`Startup.ConfigureServices`에서 `AddIdentityUI` 메서드 호출에 대한 매개 변수를 사용하여 UI 프레임워크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-112">The UI framework could be configured using a parameter to the `AddIdentityUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ba9b3-113">새 동작</span><span class="sxs-lookup"><span data-stu-id="ba9b3-113">New behavior</span></span>

<span data-ttu-id="ba9b3-114">ID UI의 기본 UI 프레임워크는 **부트스트랩 4**입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="ba9b3-115">UI 프레임워크는 `AddIdentityUI` 메서드 호출 대신 프로젝트 파일에 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-115">The UI framework must be configured in your project file, instead of in the `AddIdentityUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ba9b3-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ba9b3-116">Reason for change</span></span>

<span data-ttu-id="ba9b3-117">정적 웹 자산 기능을 채택하려면 UI 프레임워크 구성이 MSBuild로 이동해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="ba9b3-118">포함할 프레임워크를 결정하는 것은 런타임 결정이 아니라 빌드 시간 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ba9b3-119">권장 작업</span><span class="sxs-lookup"><span data-stu-id="ba9b3-119">Recommended action</span></span>

<span data-ttu-id="ba9b3-120">사이트 UI를 검토하여 새 부트스트랩 4 구성 요소가 호환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="ba9b3-121">필요한 경우 `IdentityUIFrameworkVersion` MSBuild 속성을 사용하여 부트스트랩 3으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="ba9b3-122">프로젝트 파일의 `<PropertyGroup>` 요소에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ba9b3-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="ba9b3-123">범주</span><span class="sxs-lookup"><span data-stu-id="ba9b3-123">Category</span></span>

<span data-ttu-id="ba9b3-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ba9b3-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ba9b3-125">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ba9b3-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
