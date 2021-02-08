---
description: '자세히 알아보기: 방법: 개인 저장소 필드 지정'
title: '방법: 전용 스토리지 필드 지정'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: 09f3566ca85a69f27794329ae12fc45d88bb518c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785902"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="bc9f9-103">방법: 전용 스토리지 필드 지정</span><span class="sxs-lookup"><span data-stu-id="bc9f9-103">How to: Specify Private Storage Fields</span></span>

<span data-ttu-id="bc9f9-104">특성의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성을 사용 <xref:System.Data.Linq.Mapping.DataAttribute> 하 여 기본 저장소 필드의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="bc9f9-105">코드 예는 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-105">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="bc9f9-106">기본 스토리지 필드의 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="bc9f9-106">To specify the name of an underlying storage field</span></span>  
  
1. <span data-ttu-id="bc9f9-107"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-107">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="bc9f9-108">필드의 이름을 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성의 값으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f9-108">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9f9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc9f9-109">See also</span></span>

- [<span data-ttu-id="bc9f9-110">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="bc9f9-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="bc9f9-111">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bc9f9-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
