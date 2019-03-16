---
title: 레코드 개수가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: c71d523406f3ffa420c36125847ab6d35a8f741c
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58037110"
---
# <a name="bad-record-number"></a><span data-ttu-id="4f62c-102">레코드 개수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f62c-102">Bad record number</span></span>
<span data-ttu-id="4f62c-103">`a FileGet`, `FilePut`, `FileGetObject`또는 `FilePutObject` 문의 레코드 번호가 0보다 작거나 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f62c-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f62c-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4f62c-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4f62c-105">레코드 번호를 생성하는 데 사용한 계산을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f62c-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="4f62c-106">레코드 번호를 계산하는 데 사용한 변수 또는 레코드 번호가 포함된 변수의 철자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f62c-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="4f62c-107">모듈에서 `Option Explicit On` 을 사용하지 않으면 철자가 잘못된 변수 이름이 암시적으로 선언되고 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f62c-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f62c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="4f62c-108">See also</span></span>

- [<span data-ttu-id="4f62c-109">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="4f62c-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
