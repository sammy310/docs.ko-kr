---
description: '자세한 정보: 배열'
title: 배열
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: 2d919d5e13a03ed1c5d090339f8f0fd9c1a79190
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642449"
---
# <a name="arrays"></a><span data-ttu-id="32aff-103">배열</span><span class="sxs-lookup"><span data-stu-id="32aff-103">Arrays</span></span>

<span data-ttu-id="32aff-104">✔️ 퍼블릭 API의 배열이 아닌 컬렉션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="32aff-104">✔️ DO prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="32aff-105">[컬렉션](guidelines-for-collections.md) 섹션에서는 컬렉션과 배열 중에서 선택하는 방법에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-105">The [Collections](guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>

 <span data-ttu-id="32aff-106">❌ 읽기 전용 배열 필드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="32aff-106">❌ DO NOT use read-only array fields.</span></span> <span data-ttu-id="32aff-107">필드 자체는 읽기 전용이며 변경할 수 없지만 배열의 요소는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-107">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>

 <span data-ttu-id="32aff-108">✔️ 다차원 배열 대신 가변 배열을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-108">✔️ CONSIDER using jagged arrays instead of multidimensional arrays.</span></span>

 <span data-ttu-id="32aff-109">가변 배열은 배열이기도 한 요소가 포함된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-109">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="32aff-110">요소를 구성하는 배열의 크기는 서로 다를 수 있습니다. 이 경우 다차원 배열보다 일부 데이터 세트(예: 스파스 행렬)에 대한 공간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-110">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="32aff-111">또한 CLR은 가변 배열에 대한 인덱스 작업을 최적화하므로 일부 시나리오에서는 런타임 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32aff-111">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>

 <span data-ttu-id="32aff-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="32aff-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="32aff-113">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="32aff-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="32aff-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32aff-114">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="32aff-115">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="32aff-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="32aff-116">사용 지침</span><span class="sxs-lookup"><span data-stu-id="32aff-116">Usage Guidelines</span></span>](usage-guidelines.md)
