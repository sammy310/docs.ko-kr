---
title: 공간 함수
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319294"
---
# <a name="spatial-functions"></a><span data-ttu-id="fe20b-102">공간 함수</span><span class="sxs-lookup"><span data-stu-id="fe20b-102">Spatial Functions</span></span>
<span data-ttu-id="fe20b-103">공간 형식의 경우 리터럴 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20b-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="fe20b-104">그러나 WKT(Well Known Text) 형식의 문자열을 사용하여 호출하는 정식 Entity Framework 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20b-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="fe20b-105">예를 들어 다음 함수 호출은 기하 도형 점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe20b-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="fe20b-106">@No__t_0 메서드에는 모든 공간 정식 Entity Framework 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20b-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="fe20b-107">함수에 전달해야 하는 매개 변수를 보려면 해당 메서드를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="fe20b-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
