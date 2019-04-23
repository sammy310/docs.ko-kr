---
title: '방법: 클래스로 테이블 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 49e7d6768d8739bba94c9e8d38bcc582c8bd6e4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073137"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="49c87-102">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="49c87-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="49c87-103">사용 된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 클래스를 데이터베이스 테이블과 연결 된 엔터티 클래스로 지정 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="49c87-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="49c87-104">데이터베이스 테이블에 클래스를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="49c87-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="49c87-105"><xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49c87-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c87-106">예제</span><span class="sxs-lookup"><span data-stu-id="49c87-106">Example</span></span>  
 <span data-ttu-id="49c87-107">다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="49c87-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="49c87-108">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49c87-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="49c87-109">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c87-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c87-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="49c87-110">See also</span></span>

- [<span data-ttu-id="49c87-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="49c87-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="49c87-112">방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="49c87-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
