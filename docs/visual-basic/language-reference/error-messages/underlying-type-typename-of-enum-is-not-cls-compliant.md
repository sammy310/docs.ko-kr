---
description: '자세한 정보: BC40032: <typename> 열거형의 내부 형식이 CLS 규격이 아님'
title: 열거형의 내부 형식 <typename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: aebee5a9e0cd7f2e780d0171ad59dcfd4fd1d940
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674794"
---
# <a name="bc40032-underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="04f6b-103">BC40032: \<typename> 열거형의 내부 형식이 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-103">BC40032: Underlying type \<typename> of Enum is not CLS-compliant</span></span>

<span data-ttu-id="04f6b-104">이 열거형에 대해 지정 된 데이터 형식이 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-104">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="04f6b-105">.NET Framework 및 Visual Basic이 데이터 형식을 지원 하기 때문에이는 구성 요소 내에서 오류가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-105">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="04f6b-106">그러나 엄격 하 게 CLS 규격 코드로 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-106">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="04f6b-107">이러한 구성 요소는 구성 요소와 성공적으로 상호 작용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-107">Such a component might not be able to interact successfully with your component.</span></span>

 <span data-ttu-id="04f6b-108">다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-108">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="04f6b-109">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04f6b-109">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="04f6b-110">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04f6b-110">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="04f6b-111">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04f6b-111">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="04f6b-112">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04f6b-112">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="04f6b-113">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-113">By default, this message is a warning.</span></span> <span data-ttu-id="04f6b-114">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04f6b-114">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="04f6b-115">**오류 ID:** BC40032</span><span class="sxs-lookup"><span data-stu-id="04f6b-115">**Error ID:** BC40032</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="04f6b-116">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="04f6b-116">To correct this error</span></span>

- <span data-ttu-id="04f6b-117">구성 요소가 다른 .NET Framework 구성 요소에만 인터페이스 하거나 다른 구성 요소와 상호 작용 하지 않는 경우 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-117">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>

- <span data-ttu-id="04f6b-118">.NET Framework 용으로 작성 되지 않은 구성 요소와 상호 작용 하는 경우 리플렉션 또는 설명서에서이 데이터 형식을 지원 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-118">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="04f6b-119">이 경우 아무것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-119">If it does, you do not need to change anything.</span></span>

- <span data-ttu-id="04f6b-120">이 데이터 형식을 지원 하지 않는 구성 요소와 상호 작용 하는 경우 가장 가까운 CLS 규격 형식으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-120">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="04f6b-121">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="04f6b-122">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="04f6b-123">Automation 또는 COM 개체와 상호 작용 하는 경우 일부 형식의 데이터 너비가 .NET Framework에 비해 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="04f6b-124">예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-124">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="04f6b-125">이러한 구성 요소에 16 비트 인수를 전달 하는 경우 `UShort` `UInteger` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f6b-125">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

## <a name="see-also"></a><span data-ttu-id="04f6b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04f6b-126">See also</span></span>

- [<span data-ttu-id="04f6b-127">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04f6b-127">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)
- [<span data-ttu-id="04f6b-128">리플렉션</span><span class="sxs-lookup"><span data-stu-id="04f6b-128">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
