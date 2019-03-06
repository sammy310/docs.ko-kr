---
title: '방법: SystemFonts 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 5ed44da316ddee5ea3a83262f913da571bf75276
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378966"
---
# <a name="how-to-use-systemfonts"></a>방법: SystemFonts 사용
정적 리소스를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.SystemFonts> 스타일 또는 단추를 사용자 지정 하기 위해 클래스입니다.  
  
## <a name="example"></a>예제  
 시스템 설정과 일관된 시각적 효과를 만들도록 지원하기 위해 시스템 리소스는 몇 가지 시스템이 결정하는 값을 리소스와 속성 모두로 노출합니다. <xref:System.Windows.SystemFonts> 정적 속성 및 런타임 시 이러한 값을 동적으로 액세스를 사용할 수 있는 리소스 키를 참조 하는 속성으로 모두 시스템 글꼴 값을 포함 하는 클래스입니다. 예를 들어 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 은 <xref:System.Windows.SystemFonts> 값 및 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 는 해당 리소스 키입니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서의 멤버를 사용할 수 있습니다 <xref:System.Windows.SystemFonts> 정적 속성 또는 동적 리소스 참조 (정적 속성 값을 키로). 애플리케이션이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 값 참조를 사용합니다.  
  
> [!NOTE]
>  리소스 키의 경우 속성 이름 뒤에 “Key”라는 접미사가 붙습니다.  
  
 다음 예제에서는 액세스의 속성을 사용 하는 방법 <xref:System.Windows.SystemFonts> 스타일을 지정 하거나 단추를 사용자 지정 하기 위해 정적 값으로. 이 태그 예제에서는 할당 <xref:System.Windows.SystemFonts> 단추에는 값입니다.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 값을 사용 하도록 <xref:System.Windows.SystemFonts> 코드에서 필요가 없습니다 정적 값 또는 동적 리소스 참조를 사용 합니다. 대신 키가 아닌 속성을 사용 합니다 <xref:System.Windows.SystemFonts> 클래스입니다. 키가 아닌 속성이 정적 속성의 런타임 동작으로 정의 된 것 이지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 호스팅될 때 시스템 속성에서 실시간으로 다시 평가 하 고 시스템 값을 사용자가 수행한 변경 작업을 제대로 고려 합니다. 다음 예제에서는 단추의 글꼴 설정을 지정하는 방법을 보여 줍니다.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.SystemFonts>
- [시스템 브러시로 영역 그리기](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [SystemParameters 사용](how-to-use-systemparameters.md)
- [시스템 글꼴 키 사용](how-to-use-system-fonts-keys.md)
- [방법 항목](resources-how-to-topics.md)
- [x:Static 태그 확장](../../xaml-services/x-static-markup-extension.md)
- [XAML 리소스](xaml-resources.md)
- [DynamicResource 태그 확장](dynamicresource-markup-extension.md)
