---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005499"
---
# <a name="-main"></a><span data-ttu-id="4f03a-102">-main</span><span class="sxs-lookup"><span data-stu-id="4f03a-102">-main</span></span>
<span data-ttu-id="4f03a-103">`Sub Main` 프로시저가 포함된 클래스 또는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f03a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f03a-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f03a-105">인수</span><span class="sxs-lookup"><span data-stu-id="4f03a-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="4f03a-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="4f03a-106">Required.</span></span> <span data-ttu-id="4f03a-107">프로그램이 시작할 때 호출될 `Sub Main` 프로시저를 포함하는 클래스 또는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="4f03a-108">**-main:module** 또는 **-main:namespace.module** 형태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f03a-109">설명</span><span class="sxs-lookup"><span data-stu-id="4f03a-109">Remarks</span></span>  
 <span data-ttu-id="4f03a-110">실행 파일 또는 Windows 실행 프로그램을 만들 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="4f03a-111">**-main** 옵션을 생략하면 컴파일러가 모든 공용 클래스 및 모듈에서 유효한 공유 `Sub Main`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="4f03a-112">`Main` 프로시저의 다양한 형태에 대한 설명은 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f03a-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="4f03a-113">`location`이 <xref:System.Windows.Forms.Form>으로부터 상속하는 클래스인 경우 컴파일러는 클래스에 `Main` 프로시저가 없는 경우 애플리케이션을 시작하는 기본 `Main` 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="4f03a-114">이를 통해 개발 환경에서 만든 코드를 명령줄에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="4f03a-115">Visual Studio 통합 개발 환경에서 -main을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4f03a-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="4f03a-116">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4f03a-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="4f03a-118">**애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="4f03a-119">**애플리케이션 프레임워크 사용** 확인란이 선택되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="4f03a-120">**시작 개체** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f03a-121">예제</span><span class="sxs-lookup"><span data-stu-id="4f03a-121">Example</span></span>  
 <span data-ttu-id="4f03a-122">다음 코드는 `Test2` 클래스에서 `Sub Main` 프로시저를 찾을 수 있도록 지정하여 `T2.vb` 및 `T3.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4f03a-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f03a-123">참조</span><span class="sxs-lookup"><span data-stu-id="4f03a-123">See also</span></span>

- [<span data-ttu-id="4f03a-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4f03a-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4f03a-125">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f03a-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="4f03a-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4f03a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4f03a-127">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="4f03a-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
