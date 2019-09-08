---
title: '방법: 열을 NULL 값을 허용하는 열로 표현'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781816"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="777a7-102">방법: 열을 NULL 값을 허용하는 열로 표현</span><span class="sxs-lookup"><span data-stu-id="777a7-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="777a7-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 특성의속성을사용하여연결된데이터베이스열에null값을포함할<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>수있도록 지정합니다<xref:System.Data.Linq.Mapping.ColumnAttribute> .</span><span class="sxs-lookup"><span data-stu-id="777a7-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="777a7-104">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="777a7-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="777a7-105">열을 null 값을 허용하는 열로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="777a7-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="777a7-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="777a7-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="777a7-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="777a7-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777a7-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="777a7-108">See also</span></span>

- [<span data-ttu-id="777a7-109">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="777a7-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="777a7-110">방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="777a7-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
