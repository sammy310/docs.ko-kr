---
title: '호환성이 손상되는 변경: PublishDepsFilePath 동작 변경'
description: 단일 파일 애플리케이션에 대해 PublishDepsFilePath MSBuild 속성이 비어 있는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/17/2020
ms.openlocfilehash: 3a32f733ceaa2a24eb55d5e89f2eb1791c277f0d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256506"
---
# <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="e65c4-103">PublishDepsFilePath 동작 변경</span><span class="sxs-lookup"><span data-stu-id="e65c4-103">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="e65c4-104">단일 파일 애플리케이션의 `PublishDepsFilePath` MSBuild 속성이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-104">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="e65c4-105">또한 비단일 파일 애플리케이션의 경우 빌드 후반까지는 *deps.json* 파일이 출력 디렉터리에 복사되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-105">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="e65c4-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e65c4-106">Version introduced</span></span>

<span data-ttu-id="e65c4-107">5.0</span><span class="sxs-lookup"><span data-stu-id="e65c4-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="e65c4-108">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e65c4-108">Change description</span></span>

<span data-ttu-id="e65c4-109">이전 .NET 버전에서 `PublishDepsFilePath` MSBuild 속성은 비단일 파일 애플리케이션의 출력 디렉터리에 있는 앱 *deps.json* 파일의 경로이며 중간 디렉터리에 있는 단일 파일 앱 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-109">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="e65c4-110">.NET 5부터 단일 파일 애플리케이션의 `PublishDepsFilePath`는 비어 있으며 새로운 `IntermediateDepsFilePath` 속성이 중간 디렉터리 내의 *deps.json* 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-110">Starting in .NET 5, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="e65c4-111">또한 비단일 파일 애플리케이션의 경우 빌드 후반까지는 *deps.json* 파일이 출력 디렉터리(`PublishDepsFilePath`에 지정된 경로)에 복사되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-111">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="e65c4-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e65c4-112">Reason for change</span></span>

<span data-ttu-id="e65c4-113">다음과 같은 몇 가지 이유로 이렇게 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-113">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="e65c4-114">.NET 5에서 [개선된 단일 파일 앱](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md)을 지원하기 위한 게시 논리의 리팩터링으로 인해.</span><span class="sxs-lookup"><span data-stu-id="e65c4-114">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="e65c4-115">단일 파일 앱에서 *deps.json* 이 이미 번들된 후에 *deps.json* 파일을 다시 작성하는 대상을 방지하기 위해(따라서 자동으로 앱에 영향을 주지 않음).</span><span class="sxs-lookup"><span data-stu-id="e65c4-115">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="e65c4-116">이러한 이유로 단일 파일 애플리케이션의 `PublishDepsFilePath`가 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-116">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e65c4-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e65c4-117">Recommended action</span></span>

<span data-ttu-id="e65c4-118">*deps.json* 파일을 다시 작성하는 대상은 일반적으로 `IntermediateDepsFilePath` 속성을 사용하여 다시 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65c4-118">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e65c4-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e65c4-119">Affected APIs</span></span>

<span data-ttu-id="e65c4-120">N/A</span><span class="sxs-lookup"><span data-stu-id="e65c4-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
