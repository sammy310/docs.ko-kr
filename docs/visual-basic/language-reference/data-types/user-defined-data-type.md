---
title: 사용자 정의 데이터 형식
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
ms.openlocfilehash: fbd9536a54d7fb471d6cb2e130b14a84e40a4940
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415494"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="a99da-102">사용자 정의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a99da-102">User-Defined Data Type</span></span>

<span data-ttu-id="a99da-103">사용자가 정의한 형식으로 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-103">Holds data in a format you define.</span></span> <span data-ttu-id="a99da-104">`Structure`문은 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-104">The `Structure` statement defines the format.</span></span>

<span data-ttu-id="a99da-105">이전 버전의 Visual Basic에서는 UDT (사용자 정의 형식)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="a99da-106">현재 버전은 UDT를 *구조체로*확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="a99da-107">구조는 다양 한 데이터 형식에 대 한 하나 이상의 *멤버* 를 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="a99da-108">Visual Basic는 구조체를 단일 단위로 처리 하지만 해당 멤버에 개별적으로 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>

## <a name="remarks"></a><span data-ttu-id="a99da-109">설명</span><span class="sxs-lookup"><span data-stu-id="a99da-109">Remarks</span></span>

<span data-ttu-id="a99da-110">구조 데이터 형식을 정의 하 고 사용 하 여 다양 한 데이터 형식을 단일 단위로 결합 해야 하거나 모든 기본 데이터 형식이 필요 하지 않은 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>

<span data-ttu-id="a99da-111">구조체 데이터 형식의 기본값은 각 멤버의 기본값 조합으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>

## <a name="declaration-format"></a><span data-ttu-id="a99da-112">선언 형식</span><span class="sxs-lookup"><span data-stu-id="a99da-112">Declaration Format</span></span>

<span data-ttu-id="a99da-113">구조체 선언은 [Structure 문으로](../statements/structure-statement.md) 시작 하 고 `End Structure` 문으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-113">A structure declaration starts with the [Structure Statement](../statements/structure-statement.md) and ends with the `End Structure` statement.</span></span> <span data-ttu-id="a99da-114">문은 구조체를 정의 하는 `Structure` 데이터 형식의 식별자 이기도 한 구조체의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="a99da-115">코드의 다른 부분은이 식별자를 사용 하 여 변수, 매개 변수 및 함수 반환 값을이 구조체의 데이터 형식으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>

<span data-ttu-id="a99da-116">및 문 간의 선언은 `Structure` `End Structure` 구조체의 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-116">The declarations between the `Structure` and `End Structure` statements define the members of the structure.</span></span>

## <a name="member-access-levels"></a><span data-ttu-id="a99da-117">멤버 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="a99da-117">Member Access Levels</span></span>

<span data-ttu-id="a99da-118">[Dim 문](../statements/dim-statement.md) 또는 [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)또는 [Private](../modifiers/private.md)와 같은 액세스 수준을 지정 하는 문을 사용 하 여 모든 멤버를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-118">You must declare every member using a [Dim Statement](../statements/dim-statement.md) or a statement that specifies access level, such as [Public](../modifiers/public.md), [Friend](../modifiers/friend.md), or [Private](../modifiers/private.md).</span></span> <span data-ttu-id="a99da-119">문을 사용 하는 경우 `Dim` 액세스 수준 기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-119">If you use a `Dim` statement, the access level defaults to public.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="a99da-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="a99da-120">Programming Tips</span></span>

- <span data-ttu-id="a99da-121">**메모리 소비**</span><span class="sxs-lookup"><span data-stu-id="a99da-121">**Memory Consumption.**</span></span> <span data-ttu-id="a99da-122">모든 복합 데이터 형식과 마찬가지로 해당 멤버의 명목상 저장소 할당을 함께 추가 하 여 구조의 총 메모리 소비량을 안전 하 게 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="a99da-123">또한 메모리의 저장소 순서가 선언 순서와 동일 하다는 것을 안전 하 게 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="a99da-124">구조의 저장소 레이아웃을 제어 해야 하는 경우에는 특성을 문에 적용할 수 있습니다 <xref:System.Runtime.InteropServices.StructLayoutAttribute> `Structure` .</span><span class="sxs-lookup"><span data-stu-id="a99da-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>

- <span data-ttu-id="a99da-125">**Interop 고려 사항.**</span><span class="sxs-lookup"><span data-stu-id="a99da-125">**Interop Considerations.**</span></span> <span data-ttu-id="a99da-126">.NET Framework 용으로 작성 되지 않은 구성 요소 (예: Automation 또는 COM 개체)와 상호 작용 하는 경우 다른 환경의 사용자 정의 형식은 Visual Basic 구조체 형식과 호환 되지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a99da-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>

- <span data-ttu-id="a99da-127">**넓혀.**</span><span class="sxs-lookup"><span data-stu-id="a99da-127">**Widening.**</span></span> <span data-ttu-id="a99da-128">구조체 데이터 형식과의 자동 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="a99da-129">[연산자 문을](../statements/operator-statement.md)사용 하 여 구조체에 변환 연산자를 정의할 수 있으며 각 변환 연산자를 또는로 선언할 수 있습니다 `Widening` `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="a99da-129">You can define conversion operators on your structure using the [Operator Statement](../statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>

- <span data-ttu-id="a99da-130">**문자를 입력 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a99da-130">**Type Characters.**</span></span> <span data-ttu-id="a99da-131">구조체 데이터 형식에는 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-131">Structure data types have no literal type character or identifier type character.</span></span>

- <span data-ttu-id="a99da-132">**Framework 형식.**</span><span class="sxs-lookup"><span data-stu-id="a99da-132">**Framework Type.**</span></span> <span data-ttu-id="a99da-133">.NET Framework에 해당 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="a99da-134">모든 구조체는 .NET Framework 클래스에서 상속 <xref:System.ValueType?displayProperty=nameWithType> 하지만 개별 구조체는에 해당 하지 않습니다 <xref:System.ValueType?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a99da-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a99da-135">예제</span><span class="sxs-lookup"><span data-stu-id="a99da-135">Example</span></span>

<span data-ttu-id="a99da-136">다음 패러다임에서는 구조체의 선언에 대 한 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a99da-136">The following paradigm shows the outline of the declaration of a structure.</span></span>

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a><span data-ttu-id="a99da-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a99da-137">See also</span></span>

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [<span data-ttu-id="a99da-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a99da-138">Data Types</span></span>](index.md)
- [<span data-ttu-id="a99da-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a99da-139">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="a99da-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="a99da-140">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="a99da-141">Structure 문</span><span class="sxs-lookup"><span data-stu-id="a99da-141">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="a99da-142">Widening</span><span class="sxs-lookup"><span data-stu-id="a99da-142">Widening</span></span>](../modifiers/widening.md)
- [<span data-ttu-id="a99da-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="a99da-143">Narrowing</span></span>](../modifiers/narrowing.md)
- [<span data-ttu-id="a99da-144">구조체</span><span class="sxs-lookup"><span data-stu-id="a99da-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a99da-145">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="a99da-145">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
