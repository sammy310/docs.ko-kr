---
description: '자세한 정보: 방법: Null 값을 허용 하도록 열 표현'
title: '방법: 열을 NULL 값을 허용하는 열로 표현'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 019affd13fa9c2629c6a0ec66c42f19842a4d824
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695907"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="1e13a-103">방법: 열을 NULL 값을 허용하는 열로 표현</span><span class="sxs-lookup"><span data-stu-id="1e13a-103">How to: Represent Columns as Allowing Null Values</span></span>

<span data-ttu-id="1e13a-104">특성의 속성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 하 여 연결 된 <xref:System.Data.Linq.Mapping.ColumnAttribute> 데이터베이스 열에 null 값을 포함할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e13a-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="1e13a-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e13a-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="1e13a-106">열을 null 값을 허용하는 열로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="1e13a-106">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="1e13a-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e13a-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="1e13a-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> 속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e13a-108">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e13a-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e13a-109">See also</span></span>

- [<span data-ttu-id="1e13a-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="1e13a-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="1e13a-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1e13a-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
