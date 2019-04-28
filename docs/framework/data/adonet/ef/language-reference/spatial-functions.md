---
title: 공간 함수
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797698"
---
# <a name="spatial-functions"></a><span data-ttu-id="ecfa6-102">공간 함수</span><span class="sxs-lookup"><span data-stu-id="ecfa6-102">Spatial Functions</span></span>
<span data-ttu-id="ecfa6-103">공간 형식의 경우 리터럴 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecfa6-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="ecfa6-104">그러나 WKT(Well Known Text) 형식의 문자열을 사용하여 호출하는 정식 Entity Framework 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecfa6-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="ecfa6-105">예를 들어 다음 함수 호출은 기하 도형 점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecfa6-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="ecfa6-106"><xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> 메서드는 모든 공간 정식 Entity Framework 메서드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecfa6-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="ecfa6-107">함수에 전달해야 하는 매개 변수를 보려면 해당 메서드를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="ecfa6-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
