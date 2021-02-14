---
description: "자세한 정보: BC30561: ' <name1> '이 (가) 모호 합니다. ' ' 네임 스페이스 또는 형식에서 가져옴 <name2>"
title: "'<name1>' 네임스페이스 또는 형식에서 가져온 '<name2>'은(는) 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30561
- bc30561
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
ms.openlocfilehash: d338d16c563be988c215dd19ac59174d79a8c7a7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483575"
---
# <a name="bc30561-name1-is-ambiguous-imported-from-the-namespaces-or-types-name2"></a><span data-ttu-id="83b7a-103">BC30561: ' \<name1> '이 (가) 모호 합니다. ' ' 네임 스페이스 또는 형식에서 가져왔습니다. \<name2></span><span class="sxs-lookup"><span data-stu-id="83b7a-103">BC30561: '\<name1>' is ambiguous, imported from the namespaces or types '\<name2>'</span></span>

<span data-ttu-id="83b7a-104">모호한 이름을 제공했으므로 다른 이름과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="83b7a-104">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="83b7a-105">Visual Basic 컴파일러에 충돌 해결 규칙이 없습니다. 이름을 명확 하 게 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b7a-105">The Visual Basic compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>

 <span data-ttu-id="83b7a-106">**오류 ID:** BC30561</span><span class="sxs-lookup"><span data-stu-id="83b7a-106">**Error ID:** BC30561</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="83b7a-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="83b7a-107">To correct this error</span></span>

- <span data-ttu-id="83b7a-108">네임 스페이스 가져오기를 제거 하 여 이름을 명확 하 게 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b7a-108">Disambiguate the name by removing namespace imports.</span></span>

- <span data-ttu-id="83b7a-109">이름을 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="83b7a-109">Fully qualify the name.</span></span>

## <a name="see-also"></a><span data-ttu-id="83b7a-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="83b7a-110">See also</span></span>

- [<span data-ttu-id="83b7a-111">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="83b7a-111">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="83b7a-112">Visual Basic의 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="83b7a-112">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="83b7a-113">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="83b7a-113">Namespace Statement</span></span>](../statements/namespace-statement.md)
