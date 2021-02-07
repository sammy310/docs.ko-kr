---
description: '자세한 정보: 방법: 기본 키 표현'
title: '방법: 기본 키 표현'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 1fbac2d60bd730718b5330bfd48910a61deae15c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723610"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="ee5ea-103">방법: 기본 키 표현</span><span class="sxs-lookup"><span data-stu-id="ee5ea-103">How to: Represent Primary Keys</span></span>

<span data-ttu-id="ee5ea-104">속성 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> <xref:System.Data.Linq.Mapping.ColumnAttribute> 또는 필드를 지정 하 여 데이터베이스 열에 대 한 기본 키를 나타내도록 특성의 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-104">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="ee5ea-105">코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ee5ea-106">에서는 기본 키로 계산된 열을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-106">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="ee5ea-107">속성 또는 필드를 기본 키로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="ee5ea-107">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="ee5ea-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-108">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="ee5ea-109">값을 `true`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-109">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5ea-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee5ea-110">See also</span></span>

- [<span data-ttu-id="ee5ea-111">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="ee5ea-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="ee5ea-112">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ee5ea-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
