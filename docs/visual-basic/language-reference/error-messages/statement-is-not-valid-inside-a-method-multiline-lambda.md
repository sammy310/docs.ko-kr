---
description: '방법에 대 한 자세한 정보: BC30024: 문은 메서드/여러 줄 람다 내에서 사용할 수 없습니다.'
title: 메서드(multiline lambda) 내에서 명령문을 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: c70e5563ab8c161966cd9790ae1f192fa5d50b17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731177"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="fe97a-103">BC30024: 문은 메서드/여러 줄 람다 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe97a-103">BC30024: Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="fe97a-104">`Sub`, `Function` , 속성 `Get` 또는 속성 프로시저 내에서 문을 사용할 수 없습니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="fe97a-104">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="fe97a-105">일부 문은 모듈 또는 클래스 수준에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe97a-105">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="fe97a-106">등의 다른 항목은 `Option Strict` 네임 스페이스 수준에 있어야 하 고 다른 모든 선언 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe97a-106">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>

 <span data-ttu-id="fe97a-107">**오류 ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="fe97a-107">**Error ID:** BC30024</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="fe97a-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="fe97a-108">To correct this error</span></span>

- <span data-ttu-id="fe97a-109">프로시저에서 문을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe97a-109">Remove the statement from the procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe97a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe97a-110">See also</span></span>

- [<span data-ttu-id="fe97a-111">Sub 문</span><span class="sxs-lookup"><span data-stu-id="fe97a-111">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="fe97a-112">Function 문</span><span class="sxs-lookup"><span data-stu-id="fe97a-112">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="fe97a-113">Get 문</span><span class="sxs-lookup"><span data-stu-id="fe97a-113">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="fe97a-114">Set 문</span><span class="sxs-lookup"><span data-stu-id="fe97a-114">Set Statement</span></span>](../statements/set-statement.md)
