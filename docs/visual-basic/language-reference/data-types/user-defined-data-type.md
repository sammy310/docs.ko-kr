---
title: 사용자 정의 데이터 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 5fe12d18c7f403c1a50ed548a260ba39e83280eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814200"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="a8770-102">사용자 정의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8770-102">User-Defined Data Type</span></span>
<span data-ttu-id="a8770-103">사용자가 정의한 형식으로 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-103">Holds data in a format you define.</span></span> <span data-ttu-id="a8770-104">`Structure` 문은 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="a8770-105">이전 버전의 Visual Basic 사용자 정의 형식 (UDT)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="a8770-106">현재 버전에는 UDT를 확장 한 *구조*합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="a8770-107">구조체는 하나 이상의 연결 *멤버* 다양 한 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="a8770-108">Visual Basic는 해당 멤버를 개별적으로 액세스할 수도 있습니다 하지만 단일 단위로 구조를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8770-109">설명</span><span class="sxs-lookup"><span data-stu-id="a8770-109">Remarks</span></span>  
 <span data-ttu-id="a8770-110">정의 하 고 다양 한 데이터 형식을 단일 단위로 결합 해야 할 때 또는 none는 기본 데이터 형식 요구에 부응 하기 때 구조 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="a8770-111">구조 데이터 형식의 기본 값 각 해당 멤버의 기본 값의 조합으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="a8770-112">선언 형식</span><span class="sxs-lookup"><span data-stu-id="a8770-112">Declaration Format</span></span>  
 <span data-ttu-id="a8770-113">구조체 선언 시작 합니다 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md) 종료는 `End Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="a8770-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="a8770-114">`Structure` 문은 구조체가 정의 하는 데이터 형식 식별자는 구조체의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="a8770-115">코드의 다른 부분 변수, 매개 변수 및 함수 반환 값이이 구조체의 데이터 형식으로 선언 하려면이 식별자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="a8770-116">사이의 선언 합니다 `Structure` 및 `End Structure` 문을 구조체의 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="a8770-117">멤버 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="a8770-117">Member Access Levels</span></span>  
 <span data-ttu-id="a8770-118">사용 하 여 모든 멤버를 선언 해야 합니다는 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) 또는 같은 액세스 수준을 지정 하는 문 [공용](../../../visual-basic/language-reference/modifiers/public.md)에 [Friend](../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="a8770-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="a8770-119">사용 하는 경우는 `Dim` 문, 공용 액세스 수준 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="a8770-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="a8770-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="a8770-121">**메모리 사용량**</span><span class="sxs-lookup"><span data-stu-id="a8770-121">**Memory Consumption.**</span></span> <span data-ttu-id="a8770-122">모든 복합 데이터 형식에서와 마찬가지로 해당 멤버의 일반 저장소 할당량을 함께 추가 하 여 구조체의 총 메모리 소비량을 안전 하 게 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="a8770-123">또한 가정할 수 없습니다는 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="a8770-124">구조체의 저장소 레이아웃을 제어 해야 하는 경우 적용할 수 있습니다 합니다 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="a8770-125">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="a8770-125">**Interop Considerations.**</span></span> <span data-ttu-id="a8770-126">.NET Framework 용으로 작성 되지 구성 요소와 상호 작용 하는, 예를 들어 자동화 개체나 COM 개체를 다른 환경에서 사용자 정의 형식을 Visual Basic을 사용 하 여 호환 되지 않음을 명심 형식을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="a8770-127">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a8770-127">**Widening.**</span></span> <span data-ttu-id="a8770-128">자동 변환이 없는 구조체 데이터 형식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="a8770-129">사용 하 여 구조체에서 변환 연산자를 정의할 수 있습니다 합니다 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), 고 되도록 각 변환 연산자를 선언할 수 있습니다 `Widening` 또는 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="a8770-130">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a8770-130">**Type Characters.**</span></span> <span data-ttu-id="a8770-131">구조 데이터 형식 식별자 형식 문자가 없거나 리터럴 형식 문자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="a8770-132">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="a8770-132">**Framework Type.**</span></span> <span data-ttu-id="a8770-133">.NET Framework에는 해당 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="a8770-134">.NET Framework 클래스에서 상속 하는 모든 구조 <xref:System.ValueType?displayProperty=nameWithType>에 있지만에 해당 하는 개별 구조가 없습니다 <xref:System.ValueType?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8770-135">예제</span><span class="sxs-lookup"><span data-stu-id="a8770-135">Example</span></span>  
 <span data-ttu-id="a8770-136">다음 패러다임 구조체 선언의 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8770-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8770-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8770-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="a8770-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8770-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a8770-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a8770-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a8770-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="a8770-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="a8770-141">Structure 문</span><span class="sxs-lookup"><span data-stu-id="a8770-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="a8770-142">확장</span><span class="sxs-lookup"><span data-stu-id="a8770-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="a8770-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="a8770-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="a8770-144">구조체</span><span class="sxs-lookup"><span data-stu-id="a8770-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a8770-145">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="a8770-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
