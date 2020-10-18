---
title: "'<membername>' 멤버의 형식이 CLS 규격이 아닙니다."
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: c8c14a2d6df8804967807af881384bc7d9ccd99f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163482"
---
# <a name="bc40025-type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="58880-102">BC40025: ' ' 멤버의 형식이 \<membername> CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58880-102">BC40025: Type of member '\<membername>' is not CLS-compliant</span></span>

<span data-ttu-id="58880-103">이 멤버에 대해 지정 된 데이터 형식은 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58880-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="58880-104">.NET Framework 및 Visual Basic이 데이터 형식을 지원 하기 때문에이는 구성 요소 내에서 오류가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58880-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="58880-105">그러나 엄격 하 게 CLS 규격 코드로 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="58880-106">이러한 구성 요소는 구성 요소와 성공적으로 상호 작용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-106">Such a component might not be able to interact successfully with your component.</span></span>

 <span data-ttu-id="58880-107">다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58880-107">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="58880-108">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58880-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="58880-109">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58880-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="58880-110">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58880-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="58880-111">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58880-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="58880-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="58880-112">By default, this message is a warning.</span></span> <span data-ttu-id="58880-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58880-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="58880-114">**오류 ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="58880-114">**Error ID:** BC40025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="58880-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="58880-115">To correct this error</span></span>

- <span data-ttu-id="58880-116">구성 요소가 다른 .NET Framework 구성 요소에만 인터페이스 하거나 다른 구성 요소와 상호 작용 하지 않는 경우 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>

- <span data-ttu-id="58880-117">.NET Framework 용으로 작성 되지 않은 구성 요소와 상호 작용 하는 경우 리플렉션 또는 설명서에서이 데이터 형식을 지원 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="58880-118">이 경우 아무것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-118">If it does, you do not need to change anything.</span></span>

- <span data-ttu-id="58880-119">이 데이터 형식을 지원 하지 않는 구성 요소와 상호 작용 하는 경우 가장 가까운 CLS 규격 형식으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58880-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="58880-120">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="58880-121">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="58880-122">Automation 또는 COM 개체와 상호 작용 하는 경우 일부 형식의 데이터 너비가 .NET Framework에 비해 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="58880-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="58880-123">예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="58880-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="58880-124">이러한 구성 요소에 16 비트 인수를 전달 하는 경우 `UShort` `UInteger` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="58880-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

## <a name="see-also"></a><span data-ttu-id="58880-125">참조</span><span class="sxs-lookup"><span data-stu-id="58880-125">See also</span></span>

- [<span data-ttu-id="58880-126">리플렉션</span><span class="sxs-lookup"><span data-stu-id="58880-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
