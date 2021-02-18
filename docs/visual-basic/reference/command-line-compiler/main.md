---
description: '자세한 정보: -main'
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 4c225c5a0030de6de0aaa510080a586272aa920b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455667"
---
# <a name="-main"></a><span data-ttu-id="6af53-103">-main</span><span class="sxs-lookup"><span data-stu-id="6af53-103">-main</span></span>

<span data-ttu-id="6af53-104">`Sub Main` 프로시저가 포함된 클래스 또는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-104">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af53-105">구문</span><span class="sxs-lookup"><span data-stu-id="6af53-105">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="6af53-106">인수</span><span class="sxs-lookup"><span data-stu-id="6af53-106">Arguments</span></span>  

 `location`  
 <span data-ttu-id="6af53-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6af53-107">Required.</span></span> <span data-ttu-id="6af53-108">프로그램이 시작할 때 호출될 `Sub Main` 프로시저를 포함하는 클래스 또는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-108">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="6af53-109">**-main:module** 또는 **-main:namespace.module** 형태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-109">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6af53-110">설명</span><span class="sxs-lookup"><span data-stu-id="6af53-110">Remarks</span></span>  

 <span data-ttu-id="6af53-111">실행 파일 또는 Windows 실행 프로그램을 만들 때 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-111">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="6af53-112">**-main** 옵션을 생략하면 컴파일러가 모든 공용 클래스 및 모듈에서 유효한 공유 `Sub Main`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-112">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="6af53-113">`Main` 프로시저의 다양한 형태에 대한 설명은 [Visual Basic의 Main 프로시저](../../programming-guide/program-structure/main-procedure.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6af53-113">See [Main Procedure in Visual Basic](../../programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="6af53-114">`location`이 <xref:System.Windows.Forms.Form>으로부터 상속하는 클래스인 경우 컴파일러는 클래스에 `Main` 프로시저가 없는 경우 애플리케이션을 시작하는 기본 `Main` 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-114">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="6af53-115">이를 통해 개발 환경에서 만든 코드를 명령줄에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-115">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="6af53-116">Visual Studio 통합 개발 환경에서 -main을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="6af53-116">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="6af53-117">**솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6af53-118">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-118">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="6af53-119">**애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-119">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="6af53-120">**애플리케이션 프레임워크 사용** 확인란이 선택되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-120">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="6af53-121">**시작 개체** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-121">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af53-122">예제</span><span class="sxs-lookup"><span data-stu-id="6af53-122">Example</span></span>  

 <span data-ttu-id="6af53-123">다음 코드는 `Test2` 클래스에서 `Sub Main` 프로시저를 찾을 수 있도록 지정하여 `T2.vb` 및 `T3.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6af53-123">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="6af53-124">참조</span><span class="sxs-lookup"><span data-stu-id="6af53-124">See also</span></span>

- [<span data-ttu-id="6af53-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="6af53-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6af53-126">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6af53-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="6af53-127">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="6af53-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="6af53-128">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="6af53-128">Main Procedure in Visual Basic</span></span>](../../programming-guide/program-structure/main-procedure.md)
