---
title: '방법: 클래스 멤버로 열 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 74966dd1661faa43df334987b2e3b0e84eff3446
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037866"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="d366d-102">방법: 클래스 멤버로 열 표현</span><span class="sxs-lookup"><span data-stu-id="d366d-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="d366d-103">사용 된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> 필드 또는 속성을 데이터베이스 열과 연결할 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d366d-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="d366d-104">필드 또는 속성을 데이터베이스 열에 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="d366d-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="d366d-105"><xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 속성 또는 필드 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d366d-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d366d-106">예제</span><span class="sxs-lookup"><span data-stu-id="d366d-106">Example</span></span>  
 <span data-ttu-id="d366d-107">다음 코드에서는 `CustomerID` 클래스의 `Customer` 필드를 `CustomerID` 데이터베이스 테이블의 `Customers` 열에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d366d-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="d366d-108">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d366d-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="d366d-109">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d366d-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d366d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="d366d-110">See also</span></span>

- [<span data-ttu-id="d366d-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="d366d-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="d366d-112">방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d366d-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
