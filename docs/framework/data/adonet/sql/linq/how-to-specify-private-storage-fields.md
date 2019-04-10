---
title: '방법: 전용 스토리지 필드 지정'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: e0928b2f2e817c8cc936f7aa1190229842a121a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195438"
---
# <a name="how-to-specify-private-storage-fields"></a><span data-ttu-id="2ee03-102">방법: 전용 스토리지 필드 지정</span><span class="sxs-lookup"><span data-stu-id="2ee03-102">How to: Specify Private Storage Fields</span></span>
<span data-ttu-id="2ee03-103">사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성에는 <xref:System.Data.Linq.Mapping.DataAttribute> 특성을 기본 저장소 필드의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee03-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property on the <xref:System.Data.Linq.Mapping.DataAttribute> attribute to designate the name of an underlying storage field.</span></span>  
  
 <span data-ttu-id="2ee03-104">코드 예는 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ee03-104">For code examples, see <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a><span data-ttu-id="2ee03-105">기본 저장소 필드의 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="2ee03-105">To specify the name of an underlying storage field</span></span>  
  
1.  <span data-ttu-id="2ee03-106"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee03-106">Add the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="2ee03-107">필드의 이름을 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성의 값으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee03-107">Assign the name of the field as the value of the <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee03-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ee03-108">See also</span></span>

- [<span data-ttu-id="2ee03-109">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="2ee03-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="2ee03-110">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2ee03-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
