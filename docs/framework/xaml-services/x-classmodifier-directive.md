---
title: x:ClassModifier 지시문
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: fdbc69634e86992e71cfccdc080829b6b45f963c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100932"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 지시문
XAML 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다. 특히 부분을 만드는 대신 `class` 있는 `Public` 액세스 수준 (기본값), 제공 된 `x:Class` 만들어집니다는 `NotPublic` 액세스 수준입니다. 이 동작에는 생성된 된 어셈블리의 클래스에 대 한 액세스 수준에 적용 됩니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*NotPublic*|정확한 문자열을 지정 하기 위해 전달 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 비교 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 하는 코드 숨김 프로그래밍 언어에 따라 달라 집니다. 설명 부분을 참조하세요.|  
  
## <a name="dependencies"></a>종속성  
 [X:class](x-class-directive.md) 동일한 요소에도 제공 해야 하며 해당 요소는 페이지의 루트 요소 이어야 합니다. 자세한 내용은 [ \[MS XAML\] 4.3.1.8 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="remarks"></a>설명  
 변수의 `x:ClassModifier` .NET Framework XAML 서비스의 사용 프로그래밍 언어에 따라 다릅니다. 문자열을 사용 하 여 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 반환에 대 한 의미를 정의 하는 형식 변환기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부 및 합니다.  
  
-   C#, 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 는 `internal`합니다.  
  
-   Microsoft Visual Basic.net에서 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 는 `Friend`합니다.  
  
-   에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], 대상이 없습니다. 존재 XAML 컴파일을 지 원하는; 따라서 전달할 값을 지정 합니다.  
  
 지정할 수도 있습니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` C#에서는 `Public` Visual Basic의) 하지만 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 때문에 자주 수행 됩니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 이미 기본 동작입니다.  
  
 다른 값을 해당 하는 사용자 코드를 사용 하 여 액세스 수준 제한 사항 등 `private` C#에서 관련이 없는 `x:ClassModifier` 중첩된 클래스 참조 XAML을에서 지원 되지 않으므로 따라서는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 한정자는 동일한 효과가 있습니다.  
  
## <a name="security-notes"></a>보안 정보  
 에 선언 된 액세스 수준을 `x:ClassModifier` 특정 프레임 워크와 해당 기능에서 여전히 해석 됩니다. WPF에 로드 하 고 형식을 인스턴스화하는 기능이 포함 되어 있습니다. 여기서 `x:ClassModifier` 는 `internal`pack URI 참조를 통해 WPF 리소스에서 해당 클래스를 참조 하는 경우. 이 경우를 잠재적으로 다른 프레임 워크에 의해 구현 된와 같은 다른 결과로 수행에 의존 하지 `x:ClassModifier` 가능한 모든 인스턴스화를 차단 하도록 시도 합니다.  
  
## <a name="see-also"></a>참고자료

- [x:Class 지시문](x-class-directive.md)
- [WPF의 코드 숨김 및 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier 지시문](x-fieldmodifier-directive.md)
- [보안(WPF)](../wpf/security-wpf.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](types-migrated-from-wpf-to-system-xaml.md)
