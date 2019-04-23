---
title: System.Object 메서드
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097670"
---
# <a name="systemobject-methods"></a><span data-ttu-id="66a96-102">System.Object 메서드</span><span class="sxs-lookup"><span data-stu-id="66a96-102">System.Object Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="66a96-103">다음을 지원 합니다 <xref:System.Object> 메서드.</span><span class="sxs-lookup"><span data-stu-id="66a96-103">supports the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="66a96-104">에서는 다음 <xref:System.Object> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66a96-104">does not support the following <xref:System.Object> methods.</span></span>  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<span data-ttu-id="66a96-105"><xref:System.Object.ToString?displayProperty=nameWithType>, `BINARY`, `VARBINARY` 및 `IMAGE`와 같은 이진 형식의 `TIMESTAMP`입니다.</span><span class="sxs-lookup"><span data-stu-id="66a96-105"><xref:System.Object.ToString?displayProperty=nameWithType> for binary types such as `BINARY`, `VARBINARY`, `IMAGE`, and `TIMESTAMP`.</span></span>||  
  
## <a name="differences-from-net"></a><span data-ttu-id="66a96-106">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="66a96-106">Differences from .NET</span></span>  
 <span data-ttu-id="66a96-107">출력 <xref:System.Object.ToString?displayProperty=nameWithType> SQL을 사용 하 여 double에 대 한 `CONVERT`(NVARCHAR(30), @x, 2) SQL에서.</span><span class="sxs-lookup"><span data-stu-id="66a96-107">The output of <xref:System.Object.ToString?displayProperty=nameWithType> for double uses SQL `CONVERT`(NVARCHAR(30), @x, 2) on SQL.</span></span> <span data-ttu-id="66a96-108">이 경우에 SQL에서는 항상 16 진수와 0을 "0.000000000000000e+000"으로 표기하는 과학적 표기법을 사용하며</span><span class="sxs-lookup"><span data-stu-id="66a96-108">SQL always uses 16 digits and scientific notation in this case (for example, "0.000000000000000e+000" for 0).</span></span> <span data-ttu-id="66a96-109">결과적으로 <xref:System.Object.ToString?displayProperty=nameWithType> 변환에서는 .NET Framework의 <xref:System.Convert.ToString%2A?displayProperty=nameWithType>에서 생성한 문자열과 동일한 문자열을 생성하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="66a96-109">As a result, <xref:System.Object.ToString?displayProperty=nameWithType> conversion does not produce the same string as <xref:System.Convert.ToString%2A?displayProperty=nameWithType> in the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a96-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="66a96-110">See also</span></span>

- [<span data-ttu-id="66a96-111">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="66a96-111">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
