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
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350849"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="bdc24-102">샘플 컴파일 명령줄 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdc24-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="bdc24-103">Visual Studio 내에서 Visual Basic 프로그램을 컴파일하는 대신 명령줄에서 컴파일하여 실행 파일 (.exe) 또는 동적 연결 라이브러리 (.dll) 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="bdc24-104">Visual Basic 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리, 디버그 및 전처리기 옵션을 제어 하는 전체 옵션 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="bdc24-105">각 옵션은 두 가지 상호 교환 가능한 형식 (`-option` 및 `/option`에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="bdc24-106">이 문서에서는 `-option` 양식만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="bdc24-107">다음 표에서는 사용자가 직접 사용 하기 위해 수정할 수 있는 몇 가지 샘플 명령줄을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="bdc24-108">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="bdc24-108">To</span></span>|<span data-ttu-id="bdc24-109">이후</span><span class="sxs-lookup"><span data-stu-id="bdc24-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="bdc24-110">파일 .vb를 컴파일하고 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="bdc24-111">파일 .vb를 컴파일하고 파일 .dll을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="bdc24-112">파일 .vb를 컴파일하고 .exe를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="bdc24-113">파일 .vb를 컴파일하고 라이브러리와 파일 .dll 이라는 참조 어셈블리를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="bdc24-114">최적화를 사용 하 고 정의 된 `DEBUG` 기호를 사용 하 여 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다. File2를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="bdc24-115">로고 또는 경고를 표시 하지 않고 디버그 버전의 File2를 생성 하는 현재 디렉터리의 모든 Visual Basic 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="bdc24-116">현재 디렉터리에 있는 모든 Visual Basic 파일을 다른 .dll로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="bdc24-117">Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 출력 창에 컴파일러 옵션을 사용 하 여 연결 된 **vbc** 명령에 대 한 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="bdc24-118">이 정보를 표시 하려면 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)을 연 다음 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 높은 수준의 자세한 표시로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdc24-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdc24-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="bdc24-119">See also</span></span>

- [<span data-ttu-id="bdc24-120">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="bdc24-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bdc24-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="bdc24-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
