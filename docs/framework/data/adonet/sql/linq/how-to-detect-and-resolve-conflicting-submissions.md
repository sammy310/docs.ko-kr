---
title: '방법: 충돌하는 전송 검색 및 문제 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138127"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>방법: 충돌하는 전송 검색 및 문제 해결
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 여러 사용자에 의한 데이터베이스 변경으로 발생하는 충돌을 검색하고 해결하는 많은 리소스를 제공합니다. 자세한 내용은 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)합니다.  
  
## <a name="example"></a>예제  
 에서는 다음 예제는 `try` / `catch` catch를 <xref:System.Data.Linq.ChangeConflictException> 예외입니다. 각 충돌의 엔터티 및 멤버 정보는 콘솔 창에 표시됩니다.  
  
> [!NOTE]
>  정보 검색을 지원하려면 `using System.Reflection` 지시문(Visual Basic의 `Imports System.Reflection`)을 포함해야 합니다. 자세한 내용은 <xref:System.Reflection>을 참조하세요.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>참고자료

- [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
