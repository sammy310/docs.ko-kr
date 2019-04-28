---
title: "'<parametername>' 매개 변수의 형식이 CLS 규격이 아닙니다."
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: e0852536a86dd415334f95a47ceb800ed2c591ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924022"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="53e94-102">형식의 매개 변수 '\<parametername >' CLS 규격이 아님</span><span class="sxs-lookup"><span data-stu-id="53e94-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="53e94-103">으로 표시 되는 프로시저 `<CLSCompliant(True)>` 로 표시 된 형식과 매개 변수를 선언 하지만 `<CLSCompliant(False)>`는 표시 되지 않았거나, 비규격 형식 이므로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="53e94-104">프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="53e94-105">이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="53e94-106">다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="53e94-107">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53e94-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="53e94-108">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53e94-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="53e94-109">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53e94-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="53e94-110">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="53e94-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="53e94-111"><xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="53e94-112">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="53e94-113">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="53e94-114">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-114">By default, this message is a warning.</span></span> <span data-ttu-id="53e94-115">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53e94-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="53e94-116">**오류 ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="53e94-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="53e94-117">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="53e94-117">To correct this error</span></span>  
  
- <span data-ttu-id="53e94-118">이 특정 형식의 매개 변수가 프로시저를 수행 해야 하는 경우 제거를 <xref:System.CLSCompliantAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="53e94-119">프로시저는 CLS 규격일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="53e94-120">프로시저가 CLS 규격 이어야 합니다 하는 경우이 매개 변수 형식의 가장 가까운 CLS 규격 형식으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="53e94-121">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="53e94-122">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="53e94-123">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="53e94-124">예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="53e94-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="53e94-125">이러한 구성 요소에서 16 비트 정수를 수락 하는 경우로 선언 `Short` 대신 `Integer` 관리 되는 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="53e94-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>