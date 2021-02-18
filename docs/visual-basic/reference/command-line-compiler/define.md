---
description: '자세한 정보: -define(Visual Basic)'
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
ms.openlocfilehash: 9d6394ecad8e59d64ef3c51312ac85562ba3ec2c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466980"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="c2938-103">-define(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2938-103">-define (Visual Basic)</span></span>

<span data-ttu-id="c2938-104">조건부 컴파일러 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-104">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2938-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2938-105">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="c2938-106">또는</span><span class="sxs-lookup"><span data-stu-id="c2938-106">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2938-107">인수</span><span class="sxs-lookup"><span data-stu-id="c2938-107">Arguments</span></span>  
  
|<span data-ttu-id="c2938-108">용어</span><span class="sxs-lookup"><span data-stu-id="c2938-108">Term</span></span>|<span data-ttu-id="c2938-109">정의</span><span class="sxs-lookup"><span data-stu-id="c2938-109">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="c2938-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c2938-110">Required.</span></span> <span data-ttu-id="c2938-111">정의할 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-111">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="c2938-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-112">Optional.</span></span> <span data-ttu-id="c2938-113">`symbol`을 할당할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-113">The value to assign `symbol`.</span></span> <span data-ttu-id="c2938-114">`value`가 문자열이면 따옴표 대신 백슬래시/따옴표 시퀀스(\\")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-114">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="c2938-115">값을 지정하지 않으면 True가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-115">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2938-116">설명</span><span class="sxs-lookup"><span data-stu-id="c2938-116">Remarks</span></span>  

 <span data-ttu-id="c2938-117">`-define` 옵션은 `-define`로 정의된 상수가 공용상수이며 프로젝트의 모든 파일에 적용된다는 점을 제외하고 원본 파일에서 `#Const` 전처리기 지시문을 사용하는 것과 유사한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-117">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="c2938-118">이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-118">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="c2938-119">`-d`는 약식 `-define`입니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-119">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="c2938-120">쉼표를 사용해 기호 정의를 구분하여 `-define`으로 여러 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-120">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="c2938-121">Visual Studio 통합 개발 환경에서 -define을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-121">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c2938-122">1.  **솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c2938-123">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c2938-124">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-124">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c2938-125">3.  **고급** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-125">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="c2938-126">4.  **사용자 지정 상수** 상자의 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-126">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c2938-127">예제</span><span class="sxs-lookup"><span data-stu-id="c2938-127">Example</span></span>  

 <span data-ttu-id="c2938-128">다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2938-128">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="c2938-129">참조</span><span class="sxs-lookup"><span data-stu-id="c2938-129">See also</span></span>

- [<span data-ttu-id="c2938-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c2938-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c2938-131">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="c2938-131">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="c2938-132">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="c2938-132">#Const Directive</span></span>](../../language-reference/directives/const-directive.md)
- [<span data-ttu-id="c2938-133">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="c2938-133">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
