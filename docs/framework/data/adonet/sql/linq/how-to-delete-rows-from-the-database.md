---
title: '방법: 데이터베이스에서 행 삭제'
description: 테이블 관련 컬렉션에서 LINQ to SQL 개체를 제거 하 여 데이터베이스의 행을 삭제 하는 방법에 대해 알아봅니다. LINQ to SQL는 삭제를 SQL DELETE 명령으로 변환 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: d08621e834961e1db9312cac36bd2e69133142b5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286393"
---
# <a name="how-to-delete-rows-from-the-database"></a>방법: 데이터베이스에서 행 삭제

테이블 관련 컬렉션에서 해당 개체를 제거 하 여 데이터베이스의 행을 삭제할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]변경 내용을 적절 한 SQL 명령으로 변환 `DELETE` 합니다.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 하위 삭제 작업을 지원 하거나 인식 하지 않습니다. 제약 조건이 있는 테이블의 행을 삭제하려면 다음 작업 중 하나를 수행해야 합니다.

- 데이터베이스의 외래 키 제약 조건에 `ON DELETE CASCADE` 규칙을 설정합니다.

- 사용자 고유의 코드를 사용하여 부모 개체를 삭제하는 데 방해가 되는 자식 개체를 먼저 삭제합니다.

 그러지 않으면 예외가 throw됩니다. 이 항목의 뒷부분에 있는 두 번째 코드 예제를 참조하세요.

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다. 자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.
>
> Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 동일한 목적으로 저장 프로시저를 개발할 수 있습니다.

다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다. 자세한 내용은 [방법: 데이터베이스에 연결](how-to-connect-to-a-database.md)을 참조 하세요.

### <a name="to-delete-a-row-in-the-database"></a>데이터베이스에서 행을 삭제하려면

1. 삭제할 행에 대한 데이터베이스를 쿼리합니다.

2. <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> 메서드를 호출합니다.

3. 데이터베이스에 변경 내용을 전송합니다.

## <a name="example"></a>예제

첫째 코드 예제에서는 데이터베이스에서 Order #11000에 속하는 주문 상세 정보를 쿼리하고 이러한 주문 상세 정보를 삭제하도록 표시한 다음 변경 내용을 데이터베이스에 전송합니다.

[!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
[!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]

## <a name="example"></a>예제

두 번째 예제의 목표는 주문(#10250)을 제거하는 것입니다. 이 코드에서는 먼저 `OrderDetails` 테이블을 조사하여 제거할 주문에 자식 개체가 있는지 여부를 확인합니다. 주문에 자식 개체가 있으면 먼저 해당 자식을 제거한 다음 주문을 제거하도록 표시합니다. <xref:System.Data.Linq.DataContext>에서는 데이터베이스로 전달되는 삭제 명령이 데이터베이스 제약 조건을 따르도록 실제 삭제 작업을 올바른 순서대로 배치합니다.

[!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
[!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]

## <a name="see-also"></a>참고 항목

- [방법: 변경 충돌 관리](how-to-manage-change-conflicts.md)
- [방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [데이터 변경 및 변경 내용 전송](making-and-submitting-data-changes.md)
