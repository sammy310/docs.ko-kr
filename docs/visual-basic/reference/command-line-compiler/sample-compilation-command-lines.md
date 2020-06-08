---
title: 샘플 컴파일 명령줄
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 496627d3b77b0382ae7d15c8225a6fbd41f1db73
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403124"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="5fede-102">샘플 컴파일 명령줄(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fede-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="5fede-103">Visual Studio 내에서 Visual Basic 프로그램을 컴파일하는 대신 명령줄에서 컴파일하여 실행 파일(.exe) 또는 동적 연결 라이브러리(.dll) 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="5fede-104">Visual Basic 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리, 디버그 및 전처리기 옵션을 제어하는 전체 옵션 세트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="5fede-105">각 옵션은 `-option`과 `/option`의 두 가지 상호 교환 가능한 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="5fede-106">이 설명서에서는 `-option` 양식만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="5fede-107">다음 표에서는 사용자가 직접 사용하기 위해 수정할 수 있는 몇 가지 샘플 명령줄을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="5fede-108">대상</span><span class="sxs-lookup"><span data-stu-id="5fede-108">To</span></span>|<span data-ttu-id="5fede-109">기능</span><span class="sxs-lookup"><span data-stu-id="5fede-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="5fede-110">File.vb 컴파일 및 File.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="5fede-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="5fede-111">File.vb 컴파일 및 File.dll 만들기</span><span class="sxs-lookup"><span data-stu-id="5fede-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="5fede-112">File.vb 컴파일 및 My.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="5fede-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="5fede-113">File.vb를 컴파일하고 File.dll이라는 라이브러리와 참조 어셈블리를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="5fede-114">최적화가 설정되고 `DEBUG` 기호가 정의되어 File2.exe가 생성되는 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="5fede-115">로고 또는 경고를 표시하지 않고 File2.dll의 디버그 버전을 생성하여 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="5fede-116">현재 디렉터리에 있는 모든 Visual Basic 파일을 Something.dll로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="5fede-117">Visual Studio IDE를 사용하여 프로젝트를 빌드할 때 출력 창에 해당 컴파일러 옵션과 함께 연결된 **vbc** 명령에 대한 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="5fede-118">이 정보를 표시하려면 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)을 연 다음, **MSBuild 프로젝트 빌드 출력 상세도**를 **보통** 또는 더 높은 수준의 자세한 정보 표시로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fede-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fede-119">참조</span><span class="sxs-lookup"><span data-stu-id="5fede-119">See also</span></span>

- [<span data-ttu-id="5fede-120">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="5fede-120">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="5fede-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="5fede-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
