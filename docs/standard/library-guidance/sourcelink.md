---
title: 소스 링크 및 .NET 라이브러리
description: 소스 링크를 사용하여 .NET 라이브러리의 디버깅을 향상시키기 위한 모범 사례 권장 사항입니다.
ms.date: 01/15/2019
ms.openlocfilehash: 3d768ae6e79efa23a8402ea37bc34cd58cd52c8c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744545"
---
# <a name="source-link"></a><span data-ttu-id="11afc-103">소스 링크</span><span class="sxs-lookup"><span data-stu-id="11afc-103">Source Link</span></span>

<span data-ttu-id="11afc-104">소스 링크는 개발자가 NuGet에서 제공하는 .NET 어셈블리의 소스 코드 디버깅을 가능하게 해주는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="11afc-105">소스 링크는 NuGet 패키지를 만들 때 실행되며 어셈블리 및 패키지 내부에 소스 제어 메타데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="11afc-106">패키지를 다운로드하고 Visual Studio에서 소스 링크를 사용하도록 설정한 개발자는 소스 코드를 한 단계씩 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="11afc-107">소스 링크는 뛰어난 디버깅 환경을 만들기 위해 소스 제어 메타데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="11afc-108">소스 링크 데모</span><span class="sxs-lookup"><span data-stu-id="11afc-108">Source Link demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="11afc-109">소스 링크 사용</span><span class="sxs-lookup"><span data-stu-id="11afc-109">Using Source Link</span></span>

<span data-ttu-id="11afc-110">소스 링크 사용에 대한 지침은 [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="11afc-111">[NuGet 패키지 탐색기](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)를 사용하여 소스 링크 메타데이터가 패키지에 성공적으로 포함되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="11afc-112">주석 식별자가 포함된 `Repository` 메타데이터가 있는지와 .pdb 파일이 각 대상의 .dll과 함께 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="11afc-113">![NuGet 패키지 탐색기의 소스 링크](./media/sourcelink/nuget-package-explorer-sourcelink.png "NuGet 패키지 탐색기의 소스 링크")</span><span class="sxs-lookup"><span data-stu-id="11afc-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="11afc-114">✔️ 어셈블리 및 NuGet 패키지에 소스 제어 메타데이터를 추가하는 데 소스 링크를 사용하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="11afc-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="11afc-115">사용자 유형에 디버거 특성을 추가하여 개발자의 디버깅 환경을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="11afc-116"><xref:System.Diagnostics.DebuggerDisplayAttribute>는 클래스 또는 필드가 디버거 변수 창에 표시되는 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="11afc-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute>는 디버거가 코드를 한 단계씩 실행하는 대신 코드를 단계별로 실행하도록 디버거에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="11afc-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute>는 멤버가 디버거 변수 창에 표시되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="11afc-119">✔️ 기호 파일(`*.pdb`)을 사용하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="11afc-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="11afc-120">최상의 디버깅 환경을 위해서는 라이브러리에서 기호 파일을 게시하고 소스 링크를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11afc-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="11afc-121">기호 파일 및 기호 패키지에 대한 자세한 내용은 [기호 패키지](./nuget.md#symbol-packages)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11afc-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="11afc-122">[이전](dependencies.md)
>[다음](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="11afc-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
