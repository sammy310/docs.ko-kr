---
title: "'<attributename>' 특성을 여러 번 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 14145f165adf5ccd20298a70ca5596488b488b0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409961"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="53879-102">'\<attributename>' 특성을 여러 번 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53879-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="53879-103">특성은 한 번만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53879-103">The attribute can only be applied once.</span></span> <span data-ttu-id="53879-104">특성은 `AttributeUsage` 특성을 두 번 이상 적용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53879-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="53879-105">**오류 ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="53879-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="53879-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="53879-106">To correct this error</span></span>  
  
1. <span data-ttu-id="53879-107">특성이 한 번만 적용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53879-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="53879-108">개발한 사용자 지정 특성을 사용 하는 경우 `AttributeUsage` 다음 예제와 같이 특성을 변경 하 여 여러 특성 사용을 허용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53879-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53879-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53879-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="53879-110">사용자 지정 특성 만들기</span><span class="sxs-lookup"><span data-stu-id="53879-110">Creating Custom Attributes</span></span>](../../programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="53879-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="53879-111">AttributeUsage</span></span>](../../programming-guide/concepts/attributes/attributeusage.md)
