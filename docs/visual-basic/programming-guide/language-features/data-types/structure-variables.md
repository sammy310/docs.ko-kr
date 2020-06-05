---
title: 구조체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393587"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="4f9ed-102">구조체 변수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f9ed-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="4f9ed-103">구조를 만든 후에는 프로시저 수준 및 모듈 수준 변수를 해당 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="4f9ed-104">예를 들어 컴퓨터 시스템에 대 한 정보를 기록 하는 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="4f9ed-105">다음 예에 이러한 부하 분산 방식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="4f9ed-106">이제 해당 형식의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-106">You can now declare variables of that type.</span></span> <span data-ttu-id="4f9ed-107">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="4f9ed-108">클래스 및 모듈에서 [Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하 여 선언 된 구조체는 기본적으로 공용 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-108">In classes and modules, structures declared using the [Dim Statement](../../../language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="4f9ed-109">구조체를 private로 설정 하려면 [private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 구조체를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="4f9ed-110">구조 값에 대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="4f9ed-110">Access to Structure Values</span></span>

<span data-ttu-id="4f9ed-111">구조체 변수의 요소에서 값을 할당 하 고 검색 하려면를 사용할 때와 동일한 구문을 사용 하 여 개체에 대 한 속성을 설정 하 고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="4f9ed-112">`.`구조체 변수 이름과 요소 이름 사이에 멤버 액세스 연산자 ()를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="4f9ed-113">다음 예제에서는 이전에 형식으로 선언 된 변수의 요소에 액세스 합니다 `systemInfo` .</span><span class="sxs-lookup"><span data-stu-id="4f9ed-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="4f9ed-114">구조 변수 할당</span><span class="sxs-lookup"><span data-stu-id="4f9ed-114">Assigning Structure Variables</span></span>

<span data-ttu-id="4f9ed-115">둘 다 동일한 구조 유형인 경우 하나의 변수를 다른 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="4f9ed-116">이렇게 하면 한 구조체의 모든 요소가 다른 구조체의 해당 요소에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="4f9ed-117">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="4f9ed-118">구조체 요소가, 또는 배열과 같은 참조 형식이 면 `String` `Object` 데이터에 대 한 포인터가 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="4f9ed-119">이전 예제에서가 `systemInfo` 개체 변수를 포함 한 경우 앞의 예제는에서로 포인터를 복사 했 `mySystem` `yourSystem` 고 한 구조를 통해 개체의 데이터 변경 내용이 다른 구조를 통해 액세스 될 때 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f9ed-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f9ed-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f9ed-120">See also</span></span>

- [<span data-ttu-id="4f9ed-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4f9ed-121">Data Types</span></span>](index.md)
- [<span data-ttu-id="4f9ed-122">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4f9ed-122">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="4f9ed-123">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4f9ed-123">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="4f9ed-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="4f9ed-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="4f9ed-125">구조체</span><span class="sxs-lookup"><span data-stu-id="4f9ed-125">Structures</span></span>](structures.md)
- [<span data-ttu-id="4f9ed-126">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4f9ed-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="4f9ed-127">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="4f9ed-127">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="4f9ed-128">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="4f9ed-128">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="4f9ed-129">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="4f9ed-129">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="4f9ed-130">Structure 문</span><span class="sxs-lookup"><span data-stu-id="4f9ed-130">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
