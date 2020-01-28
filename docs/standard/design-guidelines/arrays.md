---
title: 배열
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741799"
---
# <a name="arrays"></a><span data-ttu-id="90a1a-102">배열</span><span class="sxs-lookup"><span data-stu-id="90a1a-102">Arrays</span></span>
<span data-ttu-id="90a1a-103">공용 Api에서 배열에 대 한 컬렉션을 사용 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="90a1a-103">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="90a1a-104">컬렉션 [섹션에서는](../../../docs/standard/design-guidelines/guidelines-for-collections.md) 컬렉션과 배열 중에서 선택 하는 방법에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="90a1a-105">❌ 읽기 전용 배열 필드를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-105">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="90a1a-106">필드 자체는 읽기 전용 이며 변경할 수 없지만 배열의 요소는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="90a1a-107">다차원 배열 대신 가변 배열을 사용 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="90a1a-107">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="90a1a-108">가변 배열은 배열인 요소가 포함 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="90a1a-109">요소를 구성 하는 배열의 크기는 서로 다를 수 있으며, 다차원 배열과 비교 하 여 일부 데이터 집합 (예: 스파스 행렬)의 공간을 낭비 하는 공간을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="90a1a-110">또한 CLR은 가변 배열에 대 한 인덱스 작업을 최적화 하므로 일부 시나리오에서는 런타임 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90a1a-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="90a1a-111">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="90a1a-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="90a1a-112">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="90a1a-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="90a1a-113">참조</span><span class="sxs-lookup"><span data-stu-id="90a1a-113">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="90a1a-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="90a1a-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="90a1a-115">사용 지침</span><span class="sxs-lookup"><span data-stu-id="90a1a-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
