---
description: '자세히 알아보기: System.object 메서드'
title: System.Object 메서드
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 88ba4cf7cfc7dc9bea565b4689f77d088d424c44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681320"
---
# <a name="systemobject-methods"></a><span data-ttu-id="3b7cb-103">System.Object 메서드</span><span class="sxs-lookup"><span data-stu-id="3b7cb-103">System.Object Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b7cb-104">에서는 다음 메서드를 지원 <xref:System.Object> 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7cb-104">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="3b7cb-105">에서는 다음 <xref:System.Object> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b7cb-105">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<span data-ttu-id="3b7cb-106"><xref:System.Object.ToString?displayProperty=nameWithType>, `BINARY`, `VARBINARY` 및 `IMAGE`와 같은 이진 형식의 `TIMESTAMP`입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7cb-106"><xref:System.Object.ToString?displayProperty=nameWithType> for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="3b7cb-107">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="3b7cb-107">Differences from .NET</span></span>  

 <span data-ttu-id="3b7cb-108">For double의 출력은 sql <xref:System.Object.ToString?displayProperty=nameWithType> `CONVERT` 에 sql (NVARCHAR (30), @x , 2)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7cb-108">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="3b7cb-109">이 경우에 SQL에서는 항상 16 진수와 0을 "0.000000000000000e+000"으로 표기하는 과학적 표기법을 사용하며</span><span class="sxs-lookup"><span data-stu-id="3b7cb-109">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="3b7cb-110">결과적으로 <xref:System.Object.ToString?displayProperty=nameWithType> 변환에서는 .NET Framework의 <xref:System.Convert.ToString%2A?displayProperty=nameWithType>에서 생성한 문자열과 동일한 문자열을 생성하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3b7cb-110">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7cb-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b7cb-111">See also</span></span>

- [<span data-ttu-id="3b7cb-112">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="3b7cb-112">Data Types and Functions</span></span>](data-types-and-functions.md)
