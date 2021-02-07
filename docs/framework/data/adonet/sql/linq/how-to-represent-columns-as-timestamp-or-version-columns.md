---
description: '자세한 정보: 방법: 타임 스탬프 또는 버전 열로 열 표현'
title: '방법: 열을 타임스탬프 또는 버전 열로 표현'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: 042e6a62c66b3f1ef522453157560e5e4c0f7de6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712508"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="f1be7-103">방법: 열을 타임스탬프 또는 버전 열로 표현</span><span class="sxs-lookup"><span data-stu-id="f1be7-103">How to: Represent Columns as Timestamp or Version Columns</span></span>

<span data-ttu-id="f1be7-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 특성의 속성을 사용 <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 필드 또는 속성을 데이터베이스 타임 스탬프 또는 버전 번호를 포함 하는 데이터베이스 열을 나타내는 것으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1be7-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="f1be7-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1be7-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="f1be7-106">타임스탬프 또는 버전 열을 나타내도록 필드 또는 속성을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="f1be7-106">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="f1be7-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1be7-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="f1be7-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 속성 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1be7-108">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1be7-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1be7-109">See also</span></span>

- [<span data-ttu-id="f1be7-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="f1be7-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f1be7-111">방법: 동시성 충돌을 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="f1be7-111">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="f1be7-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f1be7-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
