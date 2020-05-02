---
title: 명령줄에서 빌드
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344787"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="75c29-102">명령줄에서 빌드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75c29-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="75c29-103">Visual Basic 프로젝트는 하나 이상의 개별 소스 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="75c29-104">컴파일이라는 프로세스 중에 이러한 파일은 하나의 패키지(애플리케이션으로 실행할 수 있는 단일 실행 파일)로 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="75c29-105">Visual Basic은 IDE(통합 개발 환경) 내에서 프로그램을 컴파일하는 대신 명령줄 컴파일러를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="75c29-106">명령줄 컴파일러는 시스템 메모리나 스토리지 공간이 제한된 컴퓨터를 사용하거나 쓰는 경우와 같이 IDE의 전체 기능 세트가 필요하지 않은 상황을 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="75c29-107">Visual Studio IDE 내에서 원본 파일을 컴파일하려면 **Build** 메뉴에서 **Build** 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="75c29-108">Visual Studio IDE를 사용하여 프로젝트를 빌드할 때 출력 창에 연결된 **vbc** 명령과 해당 스위치에 대한 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="75c29-109">이 정보를 표시하려면 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)을 연 다음, **MSBuild 프로젝트 빌드 출력 상세도**를 **보통** 또는 더 높은 수준의 자세한 정보 표시로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="75c29-110">자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75c29-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="75c29-111">MSBuild를 사용하여 명령 프롬프트에서 프로젝트(.vbproj) 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="75c29-112">자세한 내용은 [명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference) 및 [연습: MSBuild 사용](/visualstudio/msbuild/walkthrough-using-msbuild)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75c29-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="75c29-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="75c29-113">In This Section</span></span>

<span data-ttu-id="75c29-114">[방법: 명령줄 컴파일러 호출](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="75c29-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="75c29-115">MS-DOS 프롬프트 또는 특정 하위 디렉터리에서 명령줄 컴파일러를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="75c29-116">[샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="75c29-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="75c29-117">사용자 고유의 용도에 맞게 수정할 수 있는 샘플 명령줄 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="75c29-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="75c29-118">Related Sections</span></span>

<span data-ttu-id="75c29-119">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="75c29-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="75c29-120">사전순 또는 용도별로 구성된 컴파일러 옵션 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="75c29-121">[조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="75c29-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="75c29-122">코드의 특정 섹션을 컴파일하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="75c29-123">[Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="75c29-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="75c29-124">다른 빌드에 포함할 항목을 구성하고, 프로젝트 속성을 선택하고, 프로젝트가 올바른 순서로 빌드되는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75c29-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
