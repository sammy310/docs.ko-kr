---
title: '방법: SQL 쿼리 직접 실행'
description: ExecuteQuery를 사용 하 여 쿼리를 실행 한 다음 LINQ to SQL 쿼리가 충분 하지 않은 경우 결과를 개체로 직접 변환 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 7ebd02581d789266396b58296bbd6ad312dd468e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200578"
---
# <a name="how-to-directly-execute-sql-queries"></a>방법: SQL 쿼리 직접 실행

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 작성한 쿼리를 텍스트 형식의 매개 변수가 있는 SQL 쿼리로 변환하고 SQL 서버에 전달하여 처리합니다.  
  
 SQL에서는 애플리케이션에서 로컬로 사용할 수 있는 다양한 메서드를 실행할 수 없습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이러한 로컬 메서드를 해당 작업과 SQL 환경 내부에서 사용 가능한 함수로 변환하려 합니다. .NET Framework 기본 제공 형식에 대 한 대부분의 메서드와 연산자는 SQL 명령에 직접 번역 합니다. 일부는 사용할 수 있는 함수에서 생성될 수 있습니다. 생성될 수 없는 일부는 런타임 예외를 발생시킵니다. 자세한 내용은 [SQL-CLR 형식 매핑](sql-clr-type-mapping.md)합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리가 부족하여 특수한 작업을 수행할 수 없는 경우 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드를 사용하여 SQL 쿼리를 실행하고 쿼리의 결과를 직접 개체로 변환합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `Customer` 클래스의 데이터가 두 개의 테이블(customer1 및 customer2)에 나누어져 있다고 가정합니다. 쿼리는 `Customer` 개체의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 표 형식 결과의 열 이름이 엔터티 클래스의 열 속성과 일치할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 모든 SQL 쿼리에서 개체를 만듭니다.  
  
## <a name="example"></a>예제  

 또한 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드는 매개 변수를 허용합니다. 다음의 코드를 사용하여 매개 변수가 있는 쿼리를 실행합니다.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 매개 변수는 `Console.WriteLine()` 및 `String.Format()`에서 사용되는 동일한 중괄호 표기법을 사용하여 쿼리 텍스트에서 표현됩니다. 실제로 `String.Format()` 는 사용자가 제공 하는 쿼리 문자열에서 실제로 호출 되며, 중괄호로 묶인 매개 변수를 @p0 , @p1 ..., @p (n)과 같은 생성 된 매개 변수 이름으로 대체 합니다.  
  
## <a name="see-also"></a>참고 항목

- [배경 정보](background-information.md)
- [데이터베이스 쿼리](querying-the-database.md)
