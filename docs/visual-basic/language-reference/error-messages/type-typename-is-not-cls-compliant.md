---
title: <typename>' 형식이 CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: eacf5036ebc6fc31dfa0e8de39c4fb574c9072b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386960"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="73ee8-102">\<typename>' 형식이 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="73ee8-103">변수, 속성 또는 함수 return이 CLS 규격이 아닌 데이터 형식으로 선언 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="73ee8-104">응용 프로그램의 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (cls)를 준수 하려면 cls 규격 형식만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="73ee8-105">다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="73ee8-106">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73ee8-106">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="73ee8-107">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73ee8-107">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="73ee8-108">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73ee8-108">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="73ee8-109">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="73ee8-109">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="73ee8-110">**오류 ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="73ee8-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73ee8-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="73ee8-111">To correct this error</span></span>  
  
- <span data-ttu-id="73ee8-112">응용 프로그램에서 CLS 규격을 준수 해야 하는 경우이 요소의 데이터 형식을 가장 가까운 CLS 규격 형식으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="73ee8-113">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="73ee8-114">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="73ee8-115">응용 프로그램에서 CLS 규격이 필요 하지 않은 경우에는 아무것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="73ee8-116">그러나 비준수를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73ee8-116">You should be aware of its noncompliance, however.</span></span>
