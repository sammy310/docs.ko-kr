---
title: 명령줄에서 빌드(Visual Basic)
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
ms.openlocfilehash: 798baa90308c83e42b335635fb23a9983f5180fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839386"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="648cb-102">명령줄에서 빌드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="648cb-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="648cb-103">Visual Basic 프로젝트를 하나 이상의 별도 소스 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="648cb-104">컴파일으로 알려진 프로세스 동안 이러한 파일은 모일 하나의 패키지로-응용 프로그램으로 실행할 수 있는 단일 실행 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="648cb-105">Visual Basic Visual Studio 통합된 개발 환경 (IDE) 내에서 프로그램을 컴파일하는 대신 명령줄 컴파일러를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="648cb-106">명령줄 컴파일러는 IDE의 기능 중 일부만 필요 하지는 상황을 위한-예를 들어 때 사용 하거나 제한 된 시스템 메모리 또는 저장소 공간이 있는 컴퓨터에 대 한 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="648cb-107">Visual Studio IDE 내에서 원본 파일을 컴파일하려면 선택 합니다 **빌드** 에서 명령을 합니다 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="648cb-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="648cb-108">Visual Studio IDE를 사용 하 여 프로젝트 파일을 빌드할 때 연결에 대 한 정보를 표시할 수 있습니다 **vbc** 명령 및 출력 창에 해당 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="648cb-109">이 정보를 표시 하려면 열을 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 설정한 후 합니다 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 에 **보통** 또는 더 높은 수준의 세부 정보 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="648cb-110">자세한 내용은 [방법: 보기, 저장 및 빌드 로그 파일 구성](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>  
  
 <span data-ttu-id="648cb-111">MSBuild를 사용 하 여 명령 프롬프트에서 프로젝트 (.vbproj) 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="648cb-112">자세한 내용은 [명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference) 고 [연습: MSBuild 사용](/visualstudio/msbuild/walkthrough-using-msbuild)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="648cb-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="648cb-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="648cb-113">In This Section</span></span>  
 [<span data-ttu-id="648cb-114">방법: 명령줄 컴파일러 호출</span><span class="sxs-lookup"><span data-stu-id="648cb-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="648cb-115">MS-DOS 프롬프트 또는 특정 하위 디렉터리에서 명령줄 컴파일러를 호출 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="648cb-116">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="648cb-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="648cb-117">자신의 용도 맞게 수정할 수 있는 샘플 명령줄의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="648cb-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="648cb-118">Related Sections</span></span>  
 [<span data-ttu-id="648cb-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="648cb-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="648cb-120">컴파일러 옵션을 사전순 또는 용도 따라 구성 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="648cb-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="648cb-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="648cb-122">특정 코드 부분을 컴파일하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-122">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="648cb-123">Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리</span><span class="sxs-lookup"><span data-stu-id="648cb-123">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="648cb-124">다른 빌드에 포함 될 새로운, 프로젝트 속성을 선택 하 고 올바른 순서 대로 프로젝트를 빌드하는 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="648cb-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
