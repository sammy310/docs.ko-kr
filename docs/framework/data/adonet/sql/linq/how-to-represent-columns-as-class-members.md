---
title: '방법: 클래스 멤버로 열 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166354"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="ec2bf-102">방법: 클래스 멤버로 열 표현</span><span class="sxs-lookup"><span data-stu-id="ec2bf-102">How to: Represent Columns as Class Members</span></span>

<span data-ttu-id="ec2bf-103">특성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 필드 또는 속성을 데이터베이스 열과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2bf-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="ec2bf-104">필드 또는 속성을 데이터베이스 열에 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="ec2bf-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="ec2bf-105"><xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 속성 또는 필드 선언에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2bf-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec2bf-106">예제</span><span class="sxs-lookup"><span data-stu-id="ec2bf-106">Example</span></span>  

 <span data-ttu-id="ec2bf-107">다음 코드에서는 `CustomerID` 클래스의 `Customer` 필드를 `CustomerID` 데이터베이스 테이블의 `Customers` 열에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2bf-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="ec2bf-108">이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> 속성을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2bf-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="ec2bf-109">이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec2bf-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec2bf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec2bf-110">See also</span></span>

- [<span data-ttu-id="ec2bf-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="ec2bf-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="ec2bf-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ec2bf-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
