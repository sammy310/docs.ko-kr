---
description: '자세한 정보: 방법: 계산 열 표현'
title: '방법: 계산 열 표현'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 5f3b4898cd29c148665c6696b0b3abab42bd071c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695621"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="5177d-103">방법: 계산 열 표현</span><span class="sxs-lookup"><span data-stu-id="5177d-103">How to: Represent Computed Columns</span></span>

<span data-ttu-id="5177d-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성의 속성을 사용 <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 해당 내용이 계산 결과인 열을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5177d-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="5177d-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5177d-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="5177d-106">에서는 기본 키로 계산된 열을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5177d-106">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="5177d-107">계산된 열을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="5177d-107">To represent a computed column</span></span>  
  
1. <span data-ttu-id="5177d-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5177d-108">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="5177d-109">수식의 문자열 표현을 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5177d-109">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5177d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5177d-110">See also</span></span>

- [<span data-ttu-id="5177d-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="5177d-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="5177d-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5177d-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
