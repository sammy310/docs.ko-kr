---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344770"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="4a61d-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a61d-102">-define (Visual Basic)</span></span>
<span data-ttu-id="4a61d-103">조건부 컴파일러 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a61d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a61d-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="4a61d-105">or</span><span class="sxs-lookup"><span data-stu-id="4a61d-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a61d-106">인수</span><span class="sxs-lookup"><span data-stu-id="4a61d-106">Arguments</span></span>  
  
|<span data-ttu-id="4a61d-107">용어</span><span class="sxs-lookup"><span data-stu-id="4a61d-107">Term</span></span>|<span data-ttu-id="4a61d-108">정의</span><span class="sxs-lookup"><span data-stu-id="4a61d-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="4a61d-109">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-109">Required.</span></span> <span data-ttu-id="4a61d-110">정의할 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="4a61d-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4a61d-111">Optional.</span></span> <span data-ttu-id="4a61d-112">`symbol`을 할당할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-112">The value to assign `symbol`.</span></span> <span data-ttu-id="4a61d-113">문자열이 `value` 경우 따옴표 대신 백슬래시/따옴표 ("\\")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="4a61d-114">값을 지정하지 않으면 True가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a61d-115">주의</span><span class="sxs-lookup"><span data-stu-id="4a61d-115">Remarks</span></span>  
 <span data-ttu-id="4a61d-116">`-define` 옵션은 `-define`으로 정의 된 상수가 public이 고 프로젝트의 모든 파일에 적용 된다는 점을 제외 하 고는 소스 파일에서 `#Const` 전처리기 지시문을 사용 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="4a61d-117">이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="4a61d-118">`-d`은 `-define`의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="4a61d-119">쉼표를 사용해 기호 정의를 구분하여 `-define`으로 여러 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="4a61d-120">Visual Studio 통합 개발 환경에서 /define을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4a61d-120">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4a61d-121">1. **솔루션 탐색기**에서 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4a61d-122">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4a61d-123">2. **컴파일** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4a61d-124">3. **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="4a61d-125">4. **사용자 지정 상수** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4a61d-126">예제</span><span class="sxs-lookup"><span data-stu-id="4a61d-126">Example</span></span>  
 <span data-ttu-id="4a61d-127">다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61d-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="4a61d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a61d-128">See also</span></span>

- [<span data-ttu-id="4a61d-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4a61d-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4a61d-130">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="4a61d-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="4a61d-131">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="4a61d-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="4a61d-132">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4a61d-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
