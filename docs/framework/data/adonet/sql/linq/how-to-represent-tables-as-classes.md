---
title: '방법: 클래스로 테이블 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 1169def4e0180b1d14103d4a968ff3ed56f63d0c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781754"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="750f6-102">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="750f6-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="750f6-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 특성을사용하여클래스를데이터베이스테이블과연결된<xref:System.Data.Linq.Mapping.TableAttribute> 엔터티 클래스로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="750f6-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="750f6-104">데이터베이스 테이블에 클래스를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="750f6-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="750f6-105"><xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="750f6-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="750f6-106">예제</span><span class="sxs-lookup"><span data-stu-id="750f6-106">Example</span></span>  
 <span data-ttu-id="750f6-107">다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="750f6-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="750f6-108">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="750f6-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="750f6-109">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="750f6-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750f6-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="750f6-110">See also</span></span>

- [<span data-ttu-id="750f6-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="750f6-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="750f6-112">방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="750f6-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
