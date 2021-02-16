---
description: '자세한 정보: 방법: 개체 변수 선언 및에서 개체 변수 할당 Visual Basic'
title: '방법: 개체 변수 선언 및 개체 변수에 개체 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: f79cda4507a3dbf2a6946dee7d909b6d1b10802d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481950"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="616c5-103">방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당</span><span class="sxs-lookup"><span data-stu-id="616c5-103">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="616c5-104">Dim 문에를 지정 하 여 [개체 데이터 형식의](../../../language-reference/data-types/object-data-type.md) 변수를 선언 `As Object` 합니다 [](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="616c5-104">You declare a variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="616c5-105">개체를 `=` 대입문 또는 initialization 절에서 등호 () 뒤에 배치 하 여 개체를 이러한 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-105">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="616c5-106">예</span><span class="sxs-lookup"><span data-stu-id="616c5-106">Example</span></span>

<span data-ttu-id="616c5-107">다음 예에서는 변수를 선언 하 `Object` 고 여기에 현재 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-107">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="616c5-108">변수를 선언의 일부로 초기화 하 여 선언과 할당을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-108">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="616c5-109">다음 예제는 앞의 예제와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-109">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="616c5-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="616c5-110">Compile the code</span></span>

<span data-ttu-id="616c5-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-111">This example requires:</span></span>

- <span data-ttu-id="616c5-112"><xref:System> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="616c5-112">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="616c5-113">문을 넣을 클래스, 구조체 또는 모듈 `Dim` 입니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-113">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="616c5-114">대입문을 배치 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="616c5-114">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="616c5-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="616c5-115">See also</span></span>

- [<span data-ttu-id="616c5-116">변수 선언</span><span class="sxs-lookup"><span data-stu-id="616c5-116">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="616c5-117">개체 변수</span><span class="sxs-lookup"><span data-stu-id="616c5-117">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="616c5-118">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="616c5-118">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="616c5-119">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="616c5-119">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="616c5-120">Dim 문</span><span class="sxs-lookup"><span data-stu-id="616c5-120">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="616c5-121">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="616c5-121">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="616c5-122">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="616c5-122">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
