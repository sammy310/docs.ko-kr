---
title: '방법: 명령줄 컴파일러 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344255"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="27950-102">방법: 명령줄 컴파일러 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27950-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="27950-103">명령줄(MS-DOS 프롬프트라고도 함)에서 실행 파일의 이름을 입력하여 명령줄 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="27950-104">기본 Windows 명령 프롬프트에서 컴파일하는 경우 실행 파일의 정규화된 경로를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="27950-105">이 기본 동작을 재정의하려면 Visual Studio용 개발자 명령 프롬프트를 사용하거나 PATH 환경 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="27950-106">두 방법 모두 컴파일러 이름을 입력하기만 하면 모든 디렉터리에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="27950-107">Visual Studio용 개발자 명령 프롬프트를 사용하여 컴파일러를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="27950-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="27950-108">Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="27950-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="27950-109">Visual studio가 설치되어 있는 경우 Visual Studio용 개발자 명령 프롬프트를 사용하여 컴퓨터의 모든 디렉터리에서 컴파일러에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="27950-110">Visual Studio용 개발자 명령 프롬프트를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="27950-111">명령줄에서 `vbc.exe` *sourceFileName*을 입력한 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27950-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="27950-112">예를 들어 `SourceFiles`라는 디렉터리에 소스 코드를 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 이 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="27950-113">디렉터리에 `Source.vb`라는 소스 파일이 포함된 경우 `vbc.exe Source.vb`를 입력하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="27950-114">PATH 환경 변수를 Windows 명령 프롬프트의 컴파일러로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="27950-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="27950-115">Windows 검색 기능을 사용하여 로컬 디스크에서 Vbc.exe를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="27950-116">컴파일러가 있는 디렉터리의 정확한 이름은 Windows 디렉터리의 위치와 설치된 ".NET Framework"의 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="27950-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="27950-117">".NET Framework" 버전이 둘 이상 설치되어 있는 경우 사용할 버전(일반적으로 최신 버전)을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="27950-118">**시작** 메뉴에서 **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="27950-119">**고급** 탭을 클릭한 다음 **환경 변수**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="27950-120">**시스템** 변수 창의 목록에서 **경로**를 선택하고 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="27950-121">**시스템 변수 편집** 대화 상자의 **변수 값** 필드에서 삽입 지점을 문자열의 끝 부분으로 이동하여 세미콜론(;)을 입력한 다음 1단계에서 찾은 전체 디렉터리 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="27950-122">**확인**을 클릭하여 편집 내용을 확인하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="27950-123">PATH 환경 변수를 변경한 후에는 컴퓨터의 모든 디렉터리로부터 Windows 명령 프롬프트에서 Visual Basic 컴파일러를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="27950-124">Windows 명령 프롬프트를 사용하여 컴파일러를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="27950-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="27950-125">**시작** 메뉴에서 **보조프로그램** 폴더를 클릭하고 **Windows 명령 프롬프트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="27950-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="27950-126">명령줄에서 `vbc.exe`*sourceFileName*을 입력한 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27950-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="27950-127">예를 들어 `SourceFiles`라는 디렉터리에 소스 코드를 저장한 경우 명령 프롬프트를 열고 `cd SourceFiles`를 입력하여 이 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27950-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="27950-128">디렉터리에 `Source.vb`라는 소스 파일이 포함된 경우 `vbc.exe Source.vb`를 입력하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27950-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="27950-129">참조</span><span class="sxs-lookup"><span data-stu-id="27950-129">See also</span></span>

- [<span data-ttu-id="27950-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="27950-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="27950-131">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="27950-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
