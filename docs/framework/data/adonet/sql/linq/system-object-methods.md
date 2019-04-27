---
title: System.Object 메서드
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917665"
---
# <a name="systemobject-methods"></a>System.Object 메서드
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 다음을 지원 합니다 <xref:System.Object> 메서드.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Object> 메서드를 지원하지 않습니다.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>, `BINARY`, `VARBINARY` 및 `IMAGE`와 같은 이진 형식의 `TIMESTAMP`입니다.||  
  
## <a name="differences-from-net"></a>.NET과의 차이점  
 출력 <xref:System.Object.ToString?displayProperty=nameWithType> SQL을 사용 하 여 double에 대 한 `CONVERT`(NVARCHAR(30), @x, 2) SQL에서. 이 경우에 SQL에서는 항상 16 진수와 0을 "0.000000000000000e+000"으로 표기하는 과학적 표기법을 사용하며 결과적으로 <xref:System.Object.ToString?displayProperty=nameWithType> 변환에서는 .NET Framework의 <xref:System.Convert.ToString%2A?displayProperty=nameWithType>에서 생성한 문자열과 동일한 문자열을 생성하지 못합니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
