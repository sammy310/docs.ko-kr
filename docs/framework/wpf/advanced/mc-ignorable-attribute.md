---
title: mc:Ignorable 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: e14ab0ebc7d44e2792307b16c7c0581ff7a71bc6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740818"
---
# <a name="mcignorable-attribute"></a>mc:Ignorable 특성
태그 파일에서 발견 된 XML 네임 스페이스 접두사를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 무시할 수 있는 것으로 지정 합니다. `mc:Ignorable` 특성은 사용자 지정 네임 스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리에 대 한 태그 호환성을 지원 합니다.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>XAML 특성 사용 (단일 접두사)  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>XAML 특성 사용 (두 개의 접두사)  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 등*|XML 1.0 사양에 따라 유효한 접두사 문자열입니다.|  
|*ignorableUri*|XML 1.0 사양에 따라 네임 스페이스를 지정 하는 데 사용할 수 있는 모든 유효한 URI입니다.|  
|*ThisElementCanBeIgnored*|기본 형식을 확인할 수 없는 경우 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 프로세서 구현에서 무시할 수 있는 요소입니다.|  
  
## <a name="remarks"></a>주의  
 `mc` XML 네임 스페이스 접두사는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 호환성 네임 스페이스 `http://schemas.openxmlformats.org/markup-compatibility/2006`을 매핑할 때 사용 하는 권장 접두사 규칙입니다.  
  
 요소 이름의 접두사 부분이 `mc:Ignorable`으로 식별 되는 요소나 특성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 처리할 때 오류를 발생 시 키 지 않습니다. 해당 특성을 기본 형식 또는 프로그래밍 구문으로 확인할 수 없으면 해당 요소는 무시 됩니다. 그러나 무시 된 요소는 해당 요소가 처리 되지 않는 부작용 인 추가 요소 요구 사항에 대 한 추가 구문 분석 오류를 생성할 수 있습니다. 예를 들어, 특정 요소 콘텐츠 모델에는 정확히 하나의 자식 요소가 필요할 수 있지만 지정 된 자식 요소가 `mc:Ignorable` 접두사에 있고 지정 된 자식 요소가 형식으로 확인 되지 않은 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 오류를 발생 시킬 수 있습니다.  
  
 `mc:Ignorable`는 식별자 문자열에 대 한 네임 스페이스 매핑에만 적용 됩니다. CLR 네임 스페이스와 어셈블리를 지정 하는 어셈블리에는 네임 스페이스 매핑에 적용 되지 않습니다 .이 어셈블리는 CLR 네임 스페이스와 어셈블리를 지정 합니다 (또는 현재 실행 파일을 어셈블리로 기본 지정). `mc:Ignorable`  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서를 구현 하는 경우 프로세서 구현에서는 `mc:Ignorable`로 식별 된 접두사에 의해 정규화 된 요소나 특성에 대 한 형식 확인 시 구문 분석 또는 처리 오류를 발생 시 키 지 않아야 합니다. 그러나 프로세서 구현에서는 이전에 제공 된 단일 자식 요소 예제와 같이 로드 되지 않거나 처리 하지 못한 요소의 보조 결과인 예외를 여전히 발생 시킬 수 있습니다.  
  
 기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 된 요소 내의 콘텐츠를 무시 합니다. 그러나 추가 특성인 [mc: ProcessContent 특성](mc-processcontent-attribute.md)을 지정 하 여 사용 가능한 다음 부모 요소에 의해 무시 된 요소 내에서 콘텐츠를 지속적으로 처리 해야 할 수 있습니다.  
  
 하나 이상의 공백 문자를 구분 기호로 사용 하 여 특성에 여러 접두사를 지정할 수 있습니다 (예: `mc:Ignorable="ignore1 ignore2"`).  

 `http://schemas.openxmlformats.org/markup-compatibility/2006` 네임 스페이스는 SDK의이 영역에 문서화 되지 않은 다른 요소와 특성을 정의 합니다. 자세한 내용은 [XML 태그 호환성 사양](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze 특성](presentationoptions-freeze-attribute.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [WPF의 문서](documents-in-wpf.md)
