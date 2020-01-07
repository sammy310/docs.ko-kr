---
title: '방법: 개체 변수 선언 및 개체 변수 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: eaaeda2a986584e6e1a2e0d2cda3890fb6187598
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344240"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="958f8-102">방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당</span><span class="sxs-lookup"><span data-stu-id="958f8-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="958f8-103">[Dim 문에](../../../../visual-basic/language-reference/statements/dim-statement.md)`As Object`를 지정 하 여 [개체 데이터 형식의](../../../../visual-basic/language-reference/data-types/object-data-type.md) 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="958f8-104">개체를 대입문 또는 initialization 절에서 등호 (`=`) 뒤에 배치 하 여 개체를 이러한 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="958f8-105">예</span><span class="sxs-lookup"><span data-stu-id="958f8-105">Example</span></span>

<span data-ttu-id="958f8-106">다음 예에서는 `Object` 변수를 선언 하 고 여기에 현재 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="958f8-107">변수를 선언의 일부로 초기화 하 여 선언과 할당을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="958f8-108">다음 예제는 앞의 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="958f8-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="958f8-109">Compile the code</span></span>

<span data-ttu-id="958f8-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-110">This example requires:</span></span>

- <span data-ttu-id="958f8-111"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="958f8-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="958f8-112">`Dim` 문을 넣을 클래스, 구조체 또는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="958f8-113">대입문을 배치 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="958f8-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="958f8-114">참조</span><span class="sxs-lookup"><span data-stu-id="958f8-114">See also</span></span>

- [<span data-ttu-id="958f8-115">변수 선언</span><span class="sxs-lookup"><span data-stu-id="958f8-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="958f8-116">개체 변수</span><span class="sxs-lookup"><span data-stu-id="958f8-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="958f8-117">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="958f8-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="958f8-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="958f8-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="958f8-119">Dim 문</span><span class="sxs-lookup"><span data-stu-id="958f8-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="958f8-120">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="958f8-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="958f8-121">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="958f8-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
