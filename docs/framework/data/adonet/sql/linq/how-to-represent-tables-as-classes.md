---
description: '자세히 알아보기: 방법: 테이블을 클래스로 표현'
title: '방법: 클래스로 테이블 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 9ec5b7309d7d10eaa6e4da6cd6fe4b1d03df1dd9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723584"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="9a82f-103">방법: 클래스로 테이블 표현</span><span class="sxs-lookup"><span data-stu-id="9a82f-103">How to: Represent Tables as Classes</span></span>

<span data-ttu-id="9a82f-104">특성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 하 여 클래스를 데이터베이스 테이블과 연결 된 엔터티 클래스로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a82f-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="9a82f-105">데이터베이스 테이블에 클래스를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="9a82f-105">To map a class to a database table</span></span>  
  
- <span data-ttu-id="9a82f-106"><xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9a82f-106">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a82f-107">예제</span><span class="sxs-lookup"><span data-stu-id="9a82f-107">Example</span></span>  

 <span data-ttu-id="9a82f-108">다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a82f-108">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="9a82f-109">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a82f-109">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="9a82f-110">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a82f-110">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a82f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a82f-111">See also</span></span>

- [<span data-ttu-id="9a82f-112">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="9a82f-112">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="9a82f-113">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9a82f-113">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
