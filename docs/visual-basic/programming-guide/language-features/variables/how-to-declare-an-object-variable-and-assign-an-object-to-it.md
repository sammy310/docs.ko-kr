---
title: '방법: 개체 변수를 선언 하 고 Visual Basic의 개체를 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: e172d62e5bfadded254d5a5fd25b1dcf2da9634d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663587"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="7fab2-102">방법: 개체 변수를 선언 하 고 Visual Basic의 개체를 할당</span><span class="sxs-lookup"><span data-stu-id="7fab2-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="7fab2-103">변수를 선언 하는 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) 지정 하 여 `As Object` 에 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7fab2-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="7fab2-104">등호 뒤에 개체를 배치 하 여 이러한 변수에 개체 할당 (`=`) 할당 이나 초기화 절의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fab2-105">예제</span><span class="sxs-lookup"><span data-stu-id="7fab2-105">Example</span></span>  
 <span data-ttu-id="7fab2-106">다음 예제에서는 선언는 `Object` 변수와 현재 인스턴스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="7fab2-107">변수 선언의 일부로 초기화 하 여 선언 및 할당을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="7fab2-108">다음 예제에서는 앞의 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fab2-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7fab2-109">Compiling the Code</span></span>  
 <span data-ttu-id="7fab2-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-110">This example requires:</span></span>  
  
- <span data-ttu-id="7fab2-111"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7fab2-111">A reference to the <xref:System> namespace.</span></span>  
  
- <span data-ttu-id="7fab2-112">클래스, 구조체 또는 저장할 모듈의 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
- <span data-ttu-id="7fab2-113">할당 문을 배치 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab2-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fab2-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fab2-114">See also</span></span>

- [<span data-ttu-id="7fab2-115">변수 선언</span><span class="sxs-lookup"><span data-stu-id="7fab2-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="7fab2-116">개체 변수</span><span class="sxs-lookup"><span data-stu-id="7fab2-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="7fab2-117">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="7fab2-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="7fab2-118">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7fab2-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="7fab2-119">Dim 문</span><span class="sxs-lookup"><span data-stu-id="7fab2-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="7fab2-120">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="7fab2-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="7fab2-121">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="7fab2-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
