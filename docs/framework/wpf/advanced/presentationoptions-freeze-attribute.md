---
title: PresentationOptions:Freeze 특성
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772842"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze 특성
집합의 <xref:System.Windows.Freezable.IsFrozen%2A> 상태 `true` 포함 하는에 <xref:System.Windows.Freezable> 요소입니다. 기본 동작에 대 한는 <xref:System.Windows.Freezable> 없이 `PresentationOptions:Freeze` 는 지정 된 특성 <xref:System.Windows.Freezable.IsFrozen%2A> 됩니다 `false` 로드 시간 및 일반에 의존 하는 <xref:System.Windows.Freezable> 런타임에 동작 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`PresentationOptions`|XML 네임 스페이스 접두사를 XML 1.0 사양에 따라 유효한 접두사 문자열일 수 있습니다. 접두사 `PresentationOptions` 이 설명서의 식별을 위해 사용 됩니다.|  
|`freezableElement`|요소 하나를 인스턴스화하는 파생 클래스의 <xref:System.Windows.Freezable>합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `Freeze` 특성은 유일한 특성 또는 기타 프로그래밍 요소에 정의 된는 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임 스페이스입니다. 합니다 `Freeze` 특성으로 무시할 수 있는 사용 하 여 지정 될 수 있도록 특별히이 특별 한 네임 스페이스에 존재 [mc: Ignorable 특성](mc-ignorable-attribute.md) 루트 요소 선언의 일부로 합니다. 이유는 `Freeze` 무시할 수 있어야 아닙니다 때문에 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고정할 수 있는 프로세서 구현을 <xref:System.Windows.Freezable> 로드 시이 기능은 없습니다 부분을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양.  
  
 처리 하는 기능을 `Freeze` 특성은 특히에 내장 되어를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 프로세서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 컴파일된 응용 프로그램에 대 한 합니다. 특성이 모든 클래스에서 지원 되지 않습니다 및 특성 구문이 확장 하거나 수정할 수 없습니다. 구현 하는 경우 사용자 고유의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 병렬의 동작을 중단 하도록 선택할 수 있습니다 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 경우 프로세서는 `Freeze` 특성을 <xref:System.Windows.Freezable> 로드 시 요소.  
  
 에 대 한 모든 값을 `Freeze` 이외의 특성 `true` (없습니다 대/소문자 구분)는 로드 시간 오류를 생성 합니다. (지정 하는 `Freeze` 특성은 `false` 오류가 되지 않지만 기본값을 설정 하므로 이미 `false` 아무 작업도 수행 하지).  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Freezable>
- [Freezable 개체 개요](freezable-objects-overview.md)
- [mc:Ignorable 특성](mc-ignorable-attribute.md)
