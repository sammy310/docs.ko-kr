---
title: '방법: 열을 데이터베이스에서 생성된 열로 표현'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2803697c668a8e1dbbeb426ea41b64878f70c145
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307914"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="c08ee-102">방법: 열을 데이터베이스에서 생성된 열로 표현</span><span class="sxs-lookup"><span data-stu-id="c08ee-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="c08ee-103">사용 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 나타내도록 필드 또는 속성을 데이터베이스에서 생성 된 열을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ee-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="c08ee-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c08ee-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="c08ee-105">데이터베이스에서 생성된 열을 나타내도록 필드 또는 속성을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="c08ee-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="c08ee-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ee-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="c08ee-107">속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c08ee-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08ee-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="c08ee-108">See also</span></span>

- [<span data-ttu-id="c08ee-109">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c08ee-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c08ee-110">방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c08ee-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
