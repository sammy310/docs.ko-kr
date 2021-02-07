---
description: '자세한 정보: 방법: 열을 Database-Generated 표현'
title: '방법: 열을 데이터베이스에서 생성된 열로 표현'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 01828ef3f73257d20023168f0ea471ee7e3863c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695634"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="dcf80-103">방법: 열을 데이터베이스에서 생성된 열로 표현</span><span class="sxs-lookup"><span data-stu-id="dcf80-103">How to: Represent Columns as Database-Generated</span></span>

<span data-ttu-id="dcf80-104">특성의 속성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 하 여 데이터베이스에서 생성 된 열을 <xref:System.Data.Linq.Mapping.ColumnAttribute> 나타내는 필드 또는 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf80-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="dcf80-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcf80-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="dcf80-106">데이터베이스에서 생성된 열을 나타내도록 필드 또는 속성을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="dcf80-106">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="dcf80-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf80-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="dcf80-108">속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf80-108">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf80-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcf80-109">See also</span></span>

- [<span data-ttu-id="dcf80-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="dcf80-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="dcf80-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dcf80-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
