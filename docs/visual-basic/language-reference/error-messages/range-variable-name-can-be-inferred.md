---
description: '자세한 내용은 다음에 대해 자세히 알아보세요. BC36599: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화 된 이름 에서만 유추할 수 있습니다.'
title: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: b729b6786f9b7803a794b9a4e786d94fa41a57ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792065"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="14c64-103">BC36599: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화 된 이름 에서만 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c64-103">BC36599: Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>

<span data-ttu-id="14c64-104">하나 이상의 인수를 사용 하는 프로그래밍 요소는 LINQ 쿼리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c64-104">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="14c64-105">컴파일러가 해당 프로그래밍 요소에서 범위 변수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c64-105">The compiler is unable to infer a range variable from that programming element.</span></span>

<span data-ttu-id="14c64-106">**오류 ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="14c64-106">**Error ID:** BC36599</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="14c64-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="14c64-107">To correct this error</span></span>

<span data-ttu-id="14c64-108">다음 코드와 같이 프로그래밍 요소에 대 한 명시적 변수 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c64-108">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a><span data-ttu-id="14c64-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14c64-109">See also</span></span>

- [<span data-ttu-id="14c64-110">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="14c64-110">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="14c64-111">Select 절</span><span class="sxs-lookup"><span data-stu-id="14c64-111">Select Clause</span></span>](../queries/select-clause.md)
