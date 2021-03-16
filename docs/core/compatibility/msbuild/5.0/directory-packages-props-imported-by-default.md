---
title: '호환성이 손상되는 변경: 기본적으로 Directory.Packages.props 파일을 가져옴'
description: Directory.Packages.props라는 파일이 프로젝트 폴더에 있는 경우 NuGet의 .props 파일이 해당 파일을 자동으로 가져오는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/17/2020
ms.openlocfilehash: a031d9b2bd832be06dedb20495c24075d1239b02
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256584"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="f4c40-103">기본적으로 Directory.Packages.props 파일을 가져옴</span><span class="sxs-lookup"><span data-stu-id="f4c40-103">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="f4c40-104">NuGet의 *.props* 파일은 *Directory.Packages.props* 라는 파일이 프로젝트 폴더나 상위 항목에 있는 경우 해당 파일을 자동으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-104">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f4c40-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f4c40-105">Version introduced</span></span>

<span data-ttu-id="f4c40-106">5.0</span><span class="sxs-lookup"><span data-stu-id="f4c40-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="f4c40-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f4c40-107">Change description</span></span>

<span data-ttu-id="f4c40-108">이전 .NET 버전의 경우 *Directory.Packages.props* 라는 파일이 프로젝트 파일에 있을 수 있으며, 빌드 시 NuGet의 *.props* 파일이 해당 파일을 자동으로 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-108">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="f4c40-109">.NET 5부터는 해당 파일이 프로젝트 폴더나 상위 항목에 있는 경우 파일을 자동으로 ‘가져옵니다’.</span><span class="sxs-lookup"><span data-stu-id="f4c40-109">Starting in .NET 5, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="f4c40-110">프로젝트 폴더에 이 이름을 가진 파일이 있는 경우에는 이러한 자동 가져오기로 인해 빌드의 동작이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-110">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="f4c40-111">예를 들어 파일을 가져오게 되지만 이전에는 가져오지 않았을 수 있습니다. 또는 구체적으로 가져올 때 파일을 가져온 순서가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-111">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f4c40-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f4c40-112">Reason for change</span></span>

<span data-ttu-id="f4c40-113">NuGet에 대한 [중앙 패키지 버전 관리](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions)를 지원하기 위해 이렇게 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-113">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f4c40-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f4c40-114">Recommended action</span></span>

<span data-ttu-id="f4c40-115">기존 *Directory.Packages.props* 파일을 자동으로 가져와서는 안 되는 경우 파일의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f4c40-115">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f4c40-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f4c40-116">Affected APIs</span></span>

<span data-ttu-id="f4c40-117">N/A</span><span class="sxs-lookup"><span data-stu-id="f4c40-117">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
