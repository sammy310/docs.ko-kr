---
title: '호환성이 손상되는 변경: Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759728"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="7722d-103">Blazor: 정적 웹 자산에 대한 유효성 검사 논리를 업데이트함</span><span class="sxs-lookup"><span data-stu-id="7722d-103">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="7722d-104">ASP.NET Core 3.1 및 Blazor WebAssembly 3.2에서 정적 웹 자산에 대한 충돌 유효성 검사에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-104">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="7722d-105">문제:</span><span class="sxs-lookup"><span data-stu-id="7722d-105">The issue:</span></span>

* <span data-ttu-id="7722d-106">호스트 자산과 RCL(Razor 클래스 라이브러리) 및 Blazor WebAssembly 앱의 자산 간의 적절한 충돌 검색을 방지했습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-106">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="7722d-107">기본적으로 RCL의 정적 웹 자산은 `_content/$(PackageId)` 접두사 아래에 제공되므로 대부분 Blazor WebAssembly 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-107">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7722d-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7722d-108">Version introduced</span></span>

<span data-ttu-id="7722d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="7722d-109">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="7722d-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="7722d-110">Old behavior</span></span>

<span data-ttu-id="7722d-111">개발하는 동안 RCL의 정적 웹 자산은 동일한 호스트 경로에 있는 호스트 프로젝트 자산으로 자동으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-111">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="7722d-112">*/folder/file.txt* 에서 제공되도록 정적 웹 자산을 정의한 RCL을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7722d-112">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="7722d-113">호스트가 파일을 *wwwroot/folder/file.txt* 에 배치한 경우 서버의 파일은 RCL 또는 Blazor WebAssembly 앱의 파일을 자동을 재정의했습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-113">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="7722d-114">새 동작</span><span class="sxs-lookup"><span data-stu-id="7722d-114">New behavior</span></span>

<span data-ttu-id="7722d-115">이 문제가 발생하면 ASP.NET Core에서 올바르게 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-115">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="7722d-116">적절한 조치를 취할 수 있도록 사용자에게 충돌에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-116">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7722d-117">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7722d-117">Reason for change</span></span>

<span data-ttu-id="7722d-118">정적 웹 자산은 프로젝트의 *wwwroot* 호스트에 있는 파일로 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-118">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="7722d-119">이러한 파일의 재정의를 허용하면 진단하기 어려운 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-119">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="7722d-120">따라서 게시된 앱에서 정의되지 않은 동작 변경이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-120">The result could be undefined behavior changes in published apps.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7722d-121">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7722d-121">Recommended action</span></span>

<span data-ttu-id="7722d-122">기본적으로 RCL 파일은 호스트의 파일과 충돌할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-122">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="7722d-123">RCL 파일에는 `_content/${PackageId}` 접두사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-123">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="7722d-124">Blazor WebAssembly 파일은 호스트 URL 공간의 루트에 배치되어 충돌이 더 쉽게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-124">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="7722d-125">예를 들어 Blazor WebAssembly 앱에는 *wwwroot* 폴더에도 포함될 수 있는 *favicon.ico* 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-125">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="7722d-126">충돌의 소스가 RCL 파일이면 코드가 라이브러리의 자산을 프로젝트의 *wwwroot* 폴더로 복사하고 있음을 의미하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-126">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="7722d-127">파일을 복사하는 코드를 작성하면 정적 웹 자산의 주요 목표에서 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-127">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="7722d-128">이 목표는 콘텐츠가 업데이트될 때 새 컴파일을 트리거하지 않고 브라우저에서 업데이트를 가져오는 데 기본이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-128">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="7722d-129">이 동작을 유지하고 호스트에 파일을 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-129">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="7722d-130">이렇게 하려면 사용자 지정 MSBuild 대상을 사용하여 정적 웹 자산 목록에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-130">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="7722d-131">호스트 프로젝트의 파일 대신 RCL의 파일이나 Blazor WebAssembly 앱의 파일을 사용하려면 호스트 프로젝트에서 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7722d-131">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7722d-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7722d-132">Affected APIs</span></span>

<span data-ttu-id="7722d-133">None</span><span class="sxs-lookup"><span data-stu-id="7722d-133">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
