---
description: '자세한 정보: 방법: 상속 계층 구조 매핑'
title: '방법: 상속 계층 구조 매핑'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 19d7e73dd477a474c98612fae8b0376188d1f08f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802036"
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="666a3-103">방법: 상속 계층 구조 매핑</span><span class="sxs-lookup"><span data-stu-id="666a3-103">How to: Map Inheritance Hierarchies</span></span>

<span data-ttu-id="666a3-104">LINQ에서 상속 매핑을 구현 하려면 다음 단계에 설명 된 대로 상속 계층 구조의 루트 클래스에서 특성 및 특성 속성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-104">To implement inheritance mapping in LINQ, you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="666a3-105">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 상속 계층 구조를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-105">Developers using Visual Studio can use the Object Relational Designer to map inheritance hierarchies.</span></span> <span data-ttu-id="666a3-106">[방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="666a3-106">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="666a3-107">서브클래스에는 특수 특성 또는 속성이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-107">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="666a3-108">특히 서브클래스에는 <xref:System.Data.Linq.Mapping.TableAttribute> 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-108">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="666a3-109">상속 계층 구조를 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="666a3-109">To map an inheritance hierarchy</span></span>  
  
1. <span data-ttu-id="666a3-110">루트 클래스에 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-110">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2. <span data-ttu-id="666a3-111">또한 루트 클래스에 계층 구조의 각 클래스에 대한 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-111">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3. <span data-ttu-id="666a3-112">각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-112">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="666a3-113">이 속성에는 이 데이터 행이 속한 클래스 또는 서브클래스를 나타내기 위해 데이터베이스 테이블의 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 열에 표시되는 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-113">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4. <span data-ttu-id="666a3-114">또한 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-114">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="666a3-115">이 속성에는 키 값이 의미하는 클래스 또는 서브클래스를 지정하는 값이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-115">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5. <span data-ttu-id="666a3-116"><xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성 중 하나의 특성에만 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-116">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="666a3-117">이 속성은 데이터베이스 테이블의 판별자 값이 상속 매핑의 어떠한 값 과도 일치 하지 않는 경우 *대체 (fallback)* 매핑을 지정 하는 데 사용 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-117">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6. <span data-ttu-id="666a3-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 특성에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-118">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="666a3-119">이 속성은 열에 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 값이 저장됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-119">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="666a3-120">예제</span><span class="sxs-lookup"><span data-stu-id="666a3-120">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="666a3-121">Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 상속을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-121">If you are using Visual Studio, you can use the Object Relational Designer to configure inheritance.</span></span> <span data-ttu-id="666a3-122">[방법: O/R 디자이너를 사용 하 여 상속 구성을](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="666a3-122">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="666a3-123">다음 코드 예제에서 `Vehicle` 는 루트 클래스로 정의 되 고 LINQ의 계층 구조를 설명 하기 위해 이전 단계가 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="666a3-123">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for LINQ.</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="666a3-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="666a3-124">See also</span></span>

- [<span data-ttu-id="666a3-125">상속 지원</span><span class="sxs-lookup"><span data-stu-id="666a3-125">Inheritance Support</span></span>](inheritance-support.md)
- [<span data-ttu-id="666a3-126">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="666a3-126">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
