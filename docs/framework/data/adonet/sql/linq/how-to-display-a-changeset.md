---
title: '방법: ChangeSet 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 92acee0d36634ea09c245418fcc7a8b97d208aa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903112"
---
# <a name="how-to-display-a-changeset"></a>방법: ChangeSet 표시
<xref:System.Data.Linq.DataContext>을 사용하여 <xref:System.Data.Linq.DataContext.GetChangeSet%2A>에 의해 추적된 변경 내용을 볼 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 도시가 London인 고객을 검색하여 도시를 Paris로 변경한 다음 변경 내용을 다시 데이터베이스로 전송합니다.  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 이 코드는 다음과 유사하게 출력됩니다. 맨 끝에 8개가 변경되었음을 요약하여 보여 줍니다.  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a>참고자료

- [디버깅 지원](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
