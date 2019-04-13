---
title: mc:ProcessContent 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 865b1a3ccc30ff5efab4b08956bf7ba2bba4769c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110588"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent 특성
지정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 직계 부모 요소에서 무시 될 수 있습니다 하는 경우에 요소에서는 관련 부모 요소에 의해 처리 되는 콘텐츠를 아직 해야를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지정으로 인해 프로세서 [mc: Ignorable 특성](mc-ignorable-attribute.md) . 합니다 `mc:ProcessContent` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|*ignorablePrefix*|XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.|  
|*ignorableUri*|XML 1.0 사양에 따라 네임 스페이스를 지정 하는 것에 대 한 모든 유효한 URI입니다.|  
|*ThisElementCanBeIgnored*|무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.|  
|*[content]*|*ThisElementCanBeIgnored* 무시할 수 있는 표시 됩니다. 프로세서에서 해당 요소를 무시 하면 *[콘텐츠]* 에서 처리 되 *개체*합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 무시 된 요소 내에서 콘텐츠를 무시 합니다. 특정 요소를 지정할 수 있습니다 `mc:ProcessContent`, 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 무시 요소 내에서 콘텐츠를 처리 하는 데 계속 됩니다. 이 콘텐츠는 하나 이상의 무시할 수 있는 하나 이상의 무시할 수 있는 몇 가지 태그 안에 중첩 되어 있습니다.  
  
 예를 들어는 공백 구분 기호로 사용 하 여 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:ProcessContent="ignore:Element1 ignore:Element2"`합니다.  
  
 합니다 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와의이 영역 내에서 다루지 않는 특성을 정의 하는 네임 스페이스는 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다. 자세한 내용은 [XML 태그 호환성 사양](https://go.microsoft.com/fwlink/?LinkId=73824)합니다.  
  
## <a name="see-also"></a>참고자료

- [mc:Ignorable 특성](mc-ignorable-attribute.md)
- [XAML 개요(WPF)](xaml-overview-wpf.md)
