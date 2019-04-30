---
title: '방법: 명령줄 컴파일러 (Visual Basic) 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 67cad0df3f10ff1fa1f6a58546fe150232fe1283
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032073"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="af562-102">방법: 명령줄 컴파일러 (Visual Basic) 호출</span><span class="sxs-lookup"><span data-stu-id="af562-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="af562-103">MS-DOS 프롬프트 라고도 하는 명령줄에 실행 파일의 이름을 입력 하 여 명령줄 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af562-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="af562-104">기본 Windows 명령 프롬프트에서에서 컴파일하는 경우에 실행 파일에 정규화 된 경로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="af562-105">이 기본 동작을 재정의 하려면 Visual Studio 용 개발자 명령 프롬프트를 사용 하거나 경로 환경 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="af562-106">둘 다 컴파일러 이름을 입력 하 여 모든 디렉터리에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af562-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="af562-107">Visual Studio 용 개발자 명령 프롬프트를 사용 하 여 컴파일러를 호출</span><span class="sxs-lookup"><span data-stu-id="af562-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1. <span data-ttu-id="af562-108">Microsoft Visual Studio 프로그램 그룹 내에서 Visual Studio Tools 프로그램 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af562-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2. <span data-ttu-id="af562-109">Visual Studio를 설치한 경우 컴퓨터에 모든 디렉터리에서 컴파일러에 액세스할 Visual Studio 용 개발자 명령 프롬프트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af562-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3. <span data-ttu-id="af562-110">Visual Studio 용 개발자 명령 프롬프트를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4. <span data-ttu-id="af562-111">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="af562-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="af562-112">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 하는 명령 프롬프트를 열고 입력 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="af562-113">디렉터리 라는 원본 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 있습니다 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="af562-114">Windows 명령 프롬프트에 대 한 컴파일러를 PATH 환경 변수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="af562-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="af562-115">로컬 디스크에 Vbc.exe를 찾으려면 Windows Search 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="af562-116">컴파일러 위치한 디렉터리의 정확한 이름을 Windows 디렉터리의 위치는 "" 설치 된.NET Framework의 버전에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="af562-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="af562-117">".NET Framework" 설치의 둘 이상의 버전이 있는 경우 (일반적으로 최신 버전)를 사용 하는 버전을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2. <span data-ttu-id="af562-118">사용자 **시작** 메뉴를 마우스 오른쪽 단추로 클릭 **내 컴퓨터**를 클릭 하 고 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="af562-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3. <span data-ttu-id="af562-119">클릭 합니다 **고급** 탭을 클릭 한 다음 **환경 변수**합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4. <span data-ttu-id="af562-120">에 **시스템** 변수 창 **경로** 클릭 하 고 목록에서 **편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5. <span data-ttu-id="af562-121">에 **시스템 편집** 변수 대화 상자에서 문자열의 끝에 삽입 포인터를 이동는 **변수 값** 필드 및 세미콜론 (;) 뒤에 1 단계에서에서 찾을 수 있는 전체 디렉터리 이름을 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6. <span data-ttu-id="af562-122">클릭 **확인** 편집 내용을 확인 하 여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="af562-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="af562-123">PATH 환경 변수를 변경한 후 실행할 수 있습니다 Visual Basic 컴파일러는 Windows 명령 프롬프트에서 디렉터리에서 컴퓨터에.</span><span class="sxs-lookup"><span data-stu-id="af562-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="af562-124">Windows 명령 프롬프트를 사용 하 여 컴파일러를 호출</span><span class="sxs-lookup"><span data-stu-id="af562-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1. <span data-ttu-id="af562-125">**시작** 메뉴를 클릭 합니다 **Accessories** 폴더를 연 다음 합니다 **Windows 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2. <span data-ttu-id="af562-126">명령줄에서 입력 `vbc.exe` *sourceFileName* 한 다음 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="af562-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="af562-127">예를 들어 라는 디렉터리에 소스 코드를 저장 하는 경우 `SourceFiles`, 하는 명령 프롬프트를 열고 입력 `cd SourceFiles` 해당 디렉터리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="af562-128">디렉터리 라는 원본 파일을 포함 하는 경우 `Source.vb`를 입력 하 여 컴파일할 수 있습니다 `vbc.exe Source.vb`합니다.</span><span class="sxs-lookup"><span data-stu-id="af562-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af562-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="af562-129">See also</span></span>

- [<span data-ttu-id="af562-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="af562-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="af562-131">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="af562-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
