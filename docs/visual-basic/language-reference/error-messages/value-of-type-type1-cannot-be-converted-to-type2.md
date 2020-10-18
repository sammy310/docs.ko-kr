---
title: "'type1' 형식의 값을 'type2'(으)로 변환할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 107936aa969690d0cc9fd4a2605cfceea31eeca8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161415"
---
# <a name="bc31194-value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="8652a-102">BC31194: ' type1 ' 형식의 값은 ' type2 ' (으)로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-102">BC31194: Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="8652a-103">' Type1 ' 형식의 값을 ' type2 ' (으)로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="8652a-104">' Value ' 속성을 사용 하 여 ' '의 첫 번째 요소에 대 한 문자열 값을 가져올 수 있습니다 \<parentElement> .</span><span class="sxs-lookup"><span data-stu-id="8652a-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>

 <span data-ttu-id="8652a-105">XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="8652a-106">XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-106">The XML literal cannot be implicitly cast to the specified type.</span></span>

 <span data-ttu-id="8652a-107">**오류 ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="8652a-107">**Error ID:** BC31194</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8652a-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8652a-108">To correct this error</span></span>

- <span data-ttu-id="8652a-109">XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="8652a-110">`CType` 함수, 다른 형식 변환 함수 또는 <xref:System.Convert> 클래스를 사용하여 지정된 형식으로 값을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8652a-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>

## <a name="see-also"></a><span data-ttu-id="8652a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8652a-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="8652a-112">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="8652a-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="8652a-113">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="8652a-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="8652a-114">XML</span><span class="sxs-lookup"><span data-stu-id="8652a-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
