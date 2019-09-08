---
title: '방법: 행 집합 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: 5ec188e0345140297062d0a10dfbbc4a294bbb7d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781600"
---
# <a name="how-to-return-rowsets"></a>방법: 행 집합 반환
이 예제에서는 데이터베이스의 행 집합을 반환하고 입력 매개 변수를 사용하여 결과를 필터링합니다.  
  
 행 집합을 반환 하는 저장 프로시저를 실행 하는 경우 저장 프로시저의 반환을 저장 하는 *result* 클래스를 사용 합니다. 자세한 내용은 [LINQ to SQL 소스 코드 분석](analyzing-linq-to-sql-source-code.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 고객의 행을 반환하고 입력 매개 변수를 사용하여 고객의 도시가 "London"인 행만을 반환하는 저장 프로시저를 보여 줍니다. 예제에서는 열거 가능한 `CustomersByCityResult` 클래스로 간주합니다.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [저장 프로시저](stored-procedures.md)
- [샘플 데이터베이스 다운로드](downloading-sample-databases.md)
