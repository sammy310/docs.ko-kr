---
title: '방법: 생성된 SQL 표시'
description: Log 속성을 사용 하 여 LINQ to SQL 기능을 이해 하 고 디버깅 하는 데 도움이 되도록 Log 속성을 사용 하 여 쿼리에 대해 생성 된 SQL 코드를 보는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 5e75a8aadf4631f0a6e50641db72ba7b83af41fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286380"
---
# <a name="how-to-display-generated-sql"></a>방법: 생성된 SQL 표시
<xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 쿼리에 대해 생성된 SQL 코드를 보고 프로세스를 변경할 수 있습니다. 이러한 접근 방식은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기능을 이해하고 특정 문제를 디버깅하는 데 유용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 코드를 실행하기 전에 콘솔 창에 SQL 코드를 표시합니다.  이 속성은 쿼리, 삽입, 업데이트 및 삭제 명령과 함께 사용할 수 있습니다.  
  
 콘솔 창의 줄은 다음에 나오는 Visual Basic 또는 c # 코드를 실행할 때 표시 됩니다.  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 지원](debugging-support.md)
