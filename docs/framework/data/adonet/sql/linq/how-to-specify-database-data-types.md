---
title: '방법: 데이터베이스 데이터 형식 지정'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: f070ff718ac10b9681c5ab3c0f4b46547349101b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197237"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="a83a1-102">방법: 데이터베이스 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="a83a1-102">How to: Specify Database Data Types</span></span>

<span data-ttu-id="a83a1-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 특성의 속성을 사용 <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 t-sql 테이블 선언에서 열을 정의 하는 정확한 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a83a1-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="a83a1-104"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 사용하여 데이터베이스 인스턴스를 만들려고 계획한 경우에만 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a83a1-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="a83a1-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a83a1-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="a83a1-106">T-SQL 테이블에서 데이터 형식을 정의하기 위한 텍스트를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="a83a1-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="a83a1-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a83a1-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="a83a1-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> 속성 값을 T-SQL에서 사용되는 정확한 텍스트로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a83a1-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83a1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a83a1-109">See also</span></span>

- [<span data-ttu-id="a83a1-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="a83a1-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a83a1-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a83a1-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
