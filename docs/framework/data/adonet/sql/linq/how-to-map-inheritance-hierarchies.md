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
# <a name="how-to-map-inheritance-hierarchies"></a>방법: 상속 계층 구조 매핑

LINQ에서 상속 매핑을 구현 하려면 다음 단계에 설명 된 대로 상속 계층 구조의 루트 클래스에서 특성 및 특성 속성을 지정 해야 합니다. Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 상속 계층 구조를 매핑할 수 있습니다. [방법: O/R 디자이너를 사용 하 여 상속 구성](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)을 참조 하세요.  
  
> [!NOTE]
> 서브클래스에는 특수 특성 또는 속성이 필요 없습니다. 특히 서브클래스에는 <xref:System.Data.Linq.Mapping.TableAttribute> 특성이 없습니다.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>상속 계층 구조를 매핑하려면  
  
1. 루트 클래스에 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가합니다.  
  
2. 또한 루트 클래스에 계층 구조의 각 클래스에 대한 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성을 추가합니다.  
  
3. 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 속성을 정의합니다.  
  
     이 속성에는 이 데이터 행이 속한 클래스 또는 서브클래스를 나타내기 위해 데이터베이스 테이블의 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 열에 표시되는 값이 저장됩니다.  
  
4. 또한 각 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성에 대해 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> 속성을 추가합니다.  
  
     이 속성에는 키 값이 의미하는 클래스 또는 서브클래스를 지정하는 값이 저장됩니다.  
  
5. <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> 특성 중 하나의 특성에만 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> 속성을 추가합니다.  
  
     이 속성은 데이터베이스 테이블의 판별자 값이 상속 매핑의 어떠한 값 과도 일치 하지 않는 경우 *대체 (fallback)* 매핑을 지정 하는 데 사용 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 됩니다.  
  
6. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> 특성에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
     이 속성은 열에 <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> 값이 저장됨을 의미합니다.  
  
## <a name="example"></a>예제  
  
> [!NOTE]
> Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 상속을 구성할 수 있습니다. [방법: O/R 디자이너를 사용 하 여 상속 구성을](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer) 참조 하세요.  
  
 다음 코드 예제에서 `Vehicle` 는 루트 클래스로 정의 되 고 LINQ의 계층 구조를 설명 하기 위해 이전 단계가 구현 되었습니다.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>참고 항목

- [상속 지원](inheritance-support.md)
- [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](how-to-customize-entity-classes-by-using-the-code-editor.md)
