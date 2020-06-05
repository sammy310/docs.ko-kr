---
title: '#Const 지시문'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415468"
---
# <a name="const-directive"></a><span data-ttu-id="5810d-102">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="5810d-102">#Const Directive</span></span>

<span data-ttu-id="5810d-103">Visual Basic에 대 한 조건부 컴파일러 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5810d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5810d-104">Syntax</span></span>  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5810d-105">부분</span><span class="sxs-lookup"><span data-stu-id="5810d-105">Parts</span></span>  

 `constname`  
 <span data-ttu-id="5810d-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5810d-106">Required.</span></span> <span data-ttu-id="5810d-107">정의 되는 상수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="5810d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5810d-108">Required.</span></span> <span data-ttu-id="5810d-109">리터럴, 기타 조건부 컴파일러 상수 또는를 제외한 모든 산술 연산자 또는 논리 연산자를 포함 하는 모든 조합 `Is` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5810d-110">설명</span><span class="sxs-lookup"><span data-stu-id="5810d-110">Remarks</span></span>  

 <span data-ttu-id="5810d-111">조건부 컴파일러 상수는 항상 표시 되는 파일에 대해 private입니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="5810d-112">지시문을 사용 하 여 공용 컴파일러 상수를 만들 수 없습니다 `#Const` . 사용자 인터페이스 또는 컴파일러 옵션을 사용 하 여 만들 수 있습니다 `/define` .</span><span class="sxs-lookup"><span data-stu-id="5810d-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="5810d-113">에서는 조건부 컴파일러 상수 및 리터럴만 사용할 수 있습니다 `expression` .</span><span class="sxs-lookup"><span data-stu-id="5810d-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="5810d-114">로 정의 된 표준 상수를 사용 `Const` 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="5810d-115">반대로 조건부 컴파일에만 키워드를 사용 하 여 정의 된 상수를 사용할 수 있습니다 `#Const` .</span><span class="sxs-lookup"><span data-stu-id="5810d-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="5810d-116">상수는 정의 되지 않을 수도 있으며,이 경우 값은 `Nothing` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5810d-117">예제</span><span class="sxs-lookup"><span data-stu-id="5810d-117">Example</span></span>  

 <span data-ttu-id="5810d-118">이 예제에서는 `#Const` 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5810d-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5810d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5810d-119">See also</span></span>

- [<span data-ttu-id="5810d-120">-define(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5810d-120">-define (Visual Basic)</span></span>](../../reference/command-line-compiler/define.md)
- [<span data-ttu-id="5810d-121">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="5810d-121">#If...Then...#Else Directives</span></span>](if-then-else-directives.md)
- [<span data-ttu-id="5810d-122">Const 문</span><span class="sxs-lookup"><span data-stu-id="5810d-122">Const Statement</span></span>](../statements/const-statement.md)
- [<span data-ttu-id="5810d-123">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="5810d-123">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="5810d-124">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="5810d-124">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
