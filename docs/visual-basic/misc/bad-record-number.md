---
description: '자세한 정보: 잘못 된 레코드 번호'
title: 레코드 개수가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: a250419c131f75381426705d52563732322631cb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460997"
---
# <a name="bad-record-number"></a><span data-ttu-id="c5a30-103">레코드 개수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a30-103">Bad record number</span></span>

<span data-ttu-id="c5a30-104">`a FileGet`, `FilePut`, `FileGetObject`또는 `FilePutObject` 문의 레코드 번호가 0보다 작거나 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a30-104">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5a30-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c5a30-105">To correct this error</span></span>  
  
1. <span data-ttu-id="c5a30-106">레코드 번호를 생성하는 데 사용한 계산을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a30-106">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="c5a30-107">레코드 번호를 계산하는 데 사용한 변수 또는 레코드 번호가 포함된 변수의 철자를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a30-107">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="c5a30-108">모듈에서 `Option Explicit On` 을 사용하지 않으면 철자가 잘못된 변수 이름이 암시적으로 선언되고 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a30-108">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a30-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c5a30-109">See also</span></span>

- [<span data-ttu-id="c5a30-110">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="c5a30-110">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
