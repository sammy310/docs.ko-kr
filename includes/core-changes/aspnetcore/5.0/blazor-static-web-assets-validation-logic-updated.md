---
ms.openlocfilehash: c090e99cd0569a843a4c505ad11b8da5740213e8
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440481"
---
### <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="d9cba-101">Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함</span><span class="sxs-lookup"><span data-stu-id="d9cba-101">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="d9cba-102">ASP.NET Core 3.1 및 Blazor WebAssembly 3.2에서 정적 웹 자산에 대한 충돌 유효성 검사에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-102">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="d9cba-103">문제:</span><span class="sxs-lookup"><span data-stu-id="d9cba-103">The issue:</span></span>

* <span data-ttu-id="d9cba-104">호스트 자산과 RCL(Razor 클래스 라이브러리) 및 Blazor WebAssembly 앱의 자산 간의 적절한 충돌 검색을 방지했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-104">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="d9cba-105">기본적으로 RCL의 정적 웹 자산은 `_content/$(PackageId)` 접두사 아래에 제공되므로 대부분 Blazor WebAssembly 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-105">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9cba-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d9cba-106">Version introduced</span></span>

<span data-ttu-id="d9cba-107">5.0</span><span class="sxs-lookup"><span data-stu-id="d9cba-107">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d9cba-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="d9cba-108">Old behavior</span></span>

<span data-ttu-id="d9cba-109">개발하는 동안 RCL의 정적 웹 자산은 동일한 호스트 경로에 있는 호스트 프로젝트 자산으로 자동으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-109">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="d9cba-110">*/folder/file.txt* 에서 제공되도록 정적 웹 자산을 정의한 RCL을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d9cba-110">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="d9cba-111">호스트가 파일을 *wwwroot/folder/file.txt* 에 배치한 경우 서버의 파일은 RCL 또는 Blazor WebAssembly 앱의 파일을 자동을 재정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-111">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d9cba-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="d9cba-112">New behavior</span></span>

<span data-ttu-id="d9cba-113">이 문제가 발생하면 ASP.NET Core에서 올바르게 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-113">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="d9cba-114">적절한 조치를 취할 수 있도록 사용자에게 충돌에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-114">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d9cba-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d9cba-115">Reason for change</span></span>

<span data-ttu-id="d9cba-116">정적 웹 자산은 프로젝트의 *wwwroot* 호스트에 있는 파일로 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-116">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="d9cba-117">이러한 파일의 재정의를 허용하면 진단하기 어려운 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-117">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="d9cba-118">따라서 게시된 앱에서 정의되지 않은 동작 변경이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-118">The result could be undefined behavior changes in published apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9cba-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d9cba-119">Recommended action</span></span>

<span data-ttu-id="d9cba-120">기본적으로 RCL 파일은 호스트의 파일과 충돌할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-120">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="d9cba-121">RCL 파일에는 `_content/${PackageId}` 접두사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-121">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="d9cba-122">Blazor WebAssembly 파일은 호스트 URL 공간의 루트에 배치되어 충돌이 더 쉽게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-122">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="d9cba-123">예를 들어 Blazor WebAssembly 앱에는 *wwwroot* 폴더에도 포함될 수 있는 *favicon.ico* 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-123">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="d9cba-124">충돌의 소스가 RCL 파일이면 코드가 라이브러리의 자산을 프로젝트의 *wwwroot* 폴더로 복사하고 있음을 의미하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-124">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="d9cba-125">파일을 복사하는 코드를 작성하면 정적 웹 자산의 주요 목표에서 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-125">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="d9cba-126">이 목표는 콘텐츠가 업데이트될 때 새 컴파일을 트리거하지 않고 브라우저에서 업데이트를 가져오는 데 기본이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-126">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="d9cba-127">이 동작을 유지하고 호스트에 파일을 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-127">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="d9cba-128">이렇게 하려면 사용자 지정 MSBuild 대상을 사용하여 정적 웹 자산 목록에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-128">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="d9cba-129">호스트 프로젝트의 파일 대신 RCL의 파일이나 Blazor WebAssembly 앱의 파일을 사용하려면 호스트 프로젝트에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d9cba-129">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

#### <a name="category"></a><span data-ttu-id="d9cba-130">범주</span><span class="sxs-lookup"><span data-stu-id="d9cba-130">Category</span></span>

<span data-ttu-id="d9cba-131">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d9cba-131">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9cba-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d9cba-132">Affected APIs</span></span>

<span data-ttu-id="d9cba-133">None</span><span class="sxs-lookup"><span data-stu-id="d9cba-133">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
