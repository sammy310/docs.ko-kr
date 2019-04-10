---
title: '방법: 기본 키 표현'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 714211046afcafab4c2b67bf9318cfbede314476
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173214"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="03f24-102">방법: 기본 키 표현</span><span class="sxs-lookup"><span data-stu-id="03f24-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="03f24-103">사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 속성에는 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성 또는 데이터베이스 열에 대 한 기본 키를 나타내는 필드를 지정 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="03f24-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="03f24-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03f24-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="03f24-105">기본 키로 계산 된 열을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03f24-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="03f24-106">속성 또는 필드를 기본 키로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="03f24-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="03f24-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03f24-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="03f24-108">값을 `true`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03f24-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f24-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="03f24-109">See also</span></span>

- [<span data-ttu-id="03f24-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="03f24-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="03f24-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="03f24-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
