---
title: 삽입, 업데이트 및 삭제 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 6a25ea5fe80da1fed16f44fd3243ebea4d64069f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230681"
---
# <a name="insert-update-and-delete-operations"></a>삽입, 업데이트 및 삭제 작업
`Insert`에서는 개체 모델에서 개체를 추가, 변경 및 제거함으로써 `Update`, `Delete` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 작업을 수행합니다. 기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 사용자 작업을 SQL로 변환하여 데이터베이스로 변경 내용을 전송합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체에 대 한 변경 내용을 유지 하 고 조작 최대한의 유연성을 제공 합니다. 엔터티 개체를 쿼리를 통해 검색하거나 새로 생성하여 사용할 수 있으면 응용 프로그램에서 해당 개체를 일반적인 개체로 변경할 수 있습니다. 즉, 해당 값을 변경할 수 있습니다, 컬렉션에 추가할 수 있습니다 및 컬렉션에서 제거할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 변경 내용을 추적 하 고 호출 하는 경우 데이터베이스에 다시 전송할 준비가 되었습니다 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 하위 삭제 작업을 인식 하거나 지원 하지 않습니다. 설정 하거나 해야 제약 조건이 있는 테이블의 행을 삭제 하려는 경우는 `ON DELETE CASCADE` 데이터베이스의 외래 키 제약 조건에 규칙 또는 사용자 고유의 코드를 사용 하 여 부모 개체 삭제 하지 못하도록 하는 자식 개체를 먼저 삭제 합니다. 그러지 않으면 예외가 throw됩니다. 자세한 내용은 [방법: 데이터베이스에서 행을 삭제할](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)합니다.  
  
 다음에 인용된 예제에서는 Northwind 샘플 데이터베이스의 `Customer`와 `Order` 클래스를 사용합니다. 간결하게 나타내기 위해 클래스 정의는 표시하지 않았습니다.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 변경 내용을 데이터베이스로 다시 전송하는 SQL 명령을 자동으로 생성하여 실행합니다.  
  
> [!NOTE]
>  일반적으로 저장 프로시저와 같은 사용자 지정 논리를 사용하여 이러한 동작을 재정의할 수 있습니다. 자세한 내용은 [는 개발자의 기본 동작 재정의의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)합니다.  
>   
>  Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 이 목적을 위해 저장된 프로시저를 개발할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [삽입, 업데이트 및 삭제 작업을 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
