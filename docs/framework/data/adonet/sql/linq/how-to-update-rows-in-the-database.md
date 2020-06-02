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
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="4c737-104">방법: 데이터베이스에서 행 업데이트</span><span class="sxs-lookup"><span data-stu-id="4c737-104">How to: Update Rows in the Database</span></span>

<span data-ttu-id="4c737-105">컬렉션과 연결 된 개체의 멤버 값을 수정한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 다음 변경 내용을 데이터베이스에 전송 하 여 데이터베이스의 행을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-105">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4c737-106">변경 내용을 적절 한 SQL 명령으로 변환 `UPDATE` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-106">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>

> [!NOTE]
> <span data-ttu-id="4c737-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-107">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="4c737-108">자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c737-108">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="4c737-109">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 동일한 목적으로 저장 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-109">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

<span data-ttu-id="4c737-110">다음 단계에서는 올바른 <xref:System.Data.Linq.DataContext>를 사용하여 사용자가 Northwind 데이터베이스에 연결되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-110">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="4c737-111">자세한 내용은 [방법: 데이터베이스에 연결](how-to-connect-to-a-database.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c737-111">For more information, see [How to: Connect to a Database](how-to-connect-to-a-database.md).</span></span>

### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="4c737-112">데이터베이스의 행을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="4c737-112">To update a row in the database</span></span>

1. <span data-ttu-id="4c737-113">업데이트할 행에 대한 데이터베이스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-113">Query the database for the row to be updated.</span></span>

2. <span data-ttu-id="4c737-114">결과 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체의 멤버 값에 대해 필요한 사항을 변경을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-114">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>

3. <span data-ttu-id="4c737-115">데이터베이스에 변경 내용을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-115">Submit the changes to the database.</span></span>

## <a name="example"></a><span data-ttu-id="4c737-116">예제</span><span class="sxs-lookup"><span data-stu-id="4c737-116">Example</span></span>

<span data-ttu-id="4c737-117">다음 예제에서는 주문 #11000에 대한 데이터베이스를 쿼리한 다음 결과 `ShipName` 개체의 `ShipVia`과 `Order`에 대한 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-117">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="4c737-118">마지막으로 이러한 멤버 값의 변경 내용을 `ShipName`과 `ShipVia` 열의 변경 내용으로 데이터베이스에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4c737-118">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>

[!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
[!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="4c737-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c737-119">See also</span></span>

- [<span data-ttu-id="4c737-120">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="4c737-120">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="4c737-121">방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="4c737-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="4c737-122">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="4c737-122">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
