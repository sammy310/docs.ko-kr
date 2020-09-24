---
title: '방법: 열을 데이터베이스에서 생성된 열로 표현'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166315"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="e3c50-102">방법: 열을 데이터베이스에서 생성된 열로 표현</span><span class="sxs-lookup"><span data-stu-id="e3c50-102">How to: Represent Columns as Database-Generated</span></span>

<span data-ttu-id="e3c50-103">특성의 속성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 하 여 데이터베이스에서 생성 된 열을 <xref:System.Data.Linq.Mapping.ColumnAttribute> 나타내는 필드 또는 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c50-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="e3c50-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3c50-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="e3c50-105">데이터베이스에서 생성된 열을 나타내도록 필드 또는 속성을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="e3c50-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="e3c50-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c50-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="e3c50-107">속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c50-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c50-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3c50-108">See also</span></span>

- [<span data-ttu-id="e3c50-109">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="e3c50-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="e3c50-110">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e3c50-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
