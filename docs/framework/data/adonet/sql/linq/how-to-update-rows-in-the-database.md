---
title: '방법: 데이터베이스에서 행 업데이트'
description: 테이블 관련 컬렉션의 LINQ to SQL 개체를 수정 하 여 데이터베이스의 행을 업데이트 하는 방법을 알아봅니다. LINQ to SQL은 SQL UPDATE 명령에 대 한 추가 내용을 변환 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: f25efb91fb5a83fb1c7c109bd018c8210edaec8b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286341"
---
# <a name="how-to-update-rows-in-the-database"></a>방법: 데이터베이스에서 행 업데이트

컬렉션과 연결 된 개체의 멤버 값을 수정한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 다음 변경 내용을 데이터베이스에 전송 하 여 데이터베이스의 행을 업데이트할 수 있습니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]변경 내용을 적절 한 SQL 명령으로 변환 `UPDATE` 합니다.

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다. 자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.
>
> Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 동일한 목적으로 저장 프로시저를 개발할 수 있습니다.

다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다. 자세한 내용은 [방법: 데이터베이스에 연결](how-to-connect-to-a-database.md)을 참조 하세요.

### <a name="to-update-a-row-in-the-database"></a>데이터베이스의 행을 업데이트하려면

1. 업데이트할 행에 대한 데이터베이스를 쿼리합니다.

2. 결과 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체의 멤버 값에 대해 필요한 사항을 변경을 합니다.

3. 데이터베이스에 변경 내용을 전송합니다.

## <a name="example"></a>예제

다음 예제에서는 주문 #11000에 대한 데이터베이스를 쿼리한 다음 결과 `ShipName` 개체의 `ShipVia`과 `Order`에 대한 값을 변경합니다. 마지막으로 이러한 멤버 값의 변경 내용을 `ShipName`과 `ShipVia` 열의 변경 내용으로 데이터베이스에 전송합니다.

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a>참고 항목

- [방법: 변경 충돌 관리](how-to-manage-change-conflicts.md)
- [방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [데이터 변경 및 변경 내용 전송](making-and-submitting-data-changes.md)
