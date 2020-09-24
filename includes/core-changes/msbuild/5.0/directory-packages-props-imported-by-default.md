---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538823"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="b3ab2-101">기본적으로 Directory.Packages.props 파일을 가져옴</span><span class="sxs-lookup"><span data-stu-id="b3ab2-101">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="b3ab2-102">NuGet의 *.props* 파일은 *Directory.Packages.props*라는 파일이 프로젝트 폴더나 상위 항목에 있는 경우 해당 파일을 자동으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-102">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b3ab2-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b3ab2-103">Version introduced</span></span>

<span data-ttu-id="b3ab2-104">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="b3ab2-104">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="b3ab2-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="b3ab2-105">Change description</span></span>

<span data-ttu-id="b3ab2-106">이전 .NET 버전의 경우 *Directory.Packages.props*라는 파일이 프로젝트 파일에 있을 수 있으며, 빌드 시 NuGet의 *.props* 파일이 해당 파일을 자동으로 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-106">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="b3ab2-107">.NET 5.0부터는 해당 파일이 프로젝트 폴더나 상위 항목에 있는 경우 파일을 자동으로 ‘가져옵니다’.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-107">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="b3ab2-108">프로젝트 폴더에 이 이름을 가진 파일이 있는 경우에는 이러한 자동 가져오기로 인해 빌드의 동작이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-108">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="b3ab2-109">예를 들어 파일을 가져오게 되지만 이전에는 가져오지 않았을 수 있습니다. 또는 구체적으로 가져올 때 파일을 가져온 순서가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-109">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b3ab2-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b3ab2-110">Reason for change</span></span>

<span data-ttu-id="b3ab2-111">NuGet에 대한 [중앙 패키지 버전 관리](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions)를 지원하기 위해 이렇게 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-111">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b3ab2-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b3ab2-112">Recommended action</span></span>

<span data-ttu-id="b3ab2-113">기존 *Directory.Packages.props* 파일을 자동으로 가져와서는 안 되는 경우 파일의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b3ab2-113">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

#### <a name="category"></a><span data-ttu-id="b3ab2-114">범주</span><span class="sxs-lookup"><span data-stu-id="b3ab2-114">Category</span></span>

<span data-ttu-id="b3ab2-115">MSBuild</span><span class="sxs-lookup"><span data-stu-id="b3ab2-115">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3ab2-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b3ab2-116">Affected APIs</span></span>

<span data-ttu-id="b3ab2-117">N/A</span><span class="sxs-lookup"><span data-stu-id="b3ab2-117">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
