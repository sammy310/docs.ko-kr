---
title: XAML 및 사용자 지정 클래스
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
ms.openlocfilehash: 4cd0ba7fa03d2578f4477c3ccf53188fbbea2dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186257"
---
# <a name="xaml-and-custom-classes-for-wpf"></a>WPF에 대한 XAML 및 사용자 지정 클래스
공통 언어 런타임(CLR) 프레임워크에서 구현된 XAML은 공통 언어 런타임(CLR) 언어에서 사용자 지정 클래스 또는 구조를 정의한 다음 XAML 태그를 사용하여 해당 클래스에 액세스하는 기능을 지원합니다. 일반적으로 사용자 지정 형식을 XAML 네임스페이스 접두사에 매핑하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 정의 형식과 사용자 지정 형식의 혼합을 동일한 태그 파일에서 함께 사용할 수 있습니다. 이 항목에서는 사용자 지정 클래스를 XAML 요소로 사용 가능하기 위해 만족해야 하는 요구 사항을 설명합니다.  

<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>
## <a name="custom-classes-in-applications-or-assemblies"></a>애플리케이션 또는 어셈블리의 사용자 지정 클래스  
 XAML에서 사용되는 사용자 지정 클래스는 두 가지 방법으로 정의할 수 있습니다. 즉, 기본 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 애플리케이션을 생성하는 다른 코드 또는 코드 숨김 파일에서 정의하거나, 클래스 라이브러리로 사용되는 DLL 또는 실행 파일과 같은 별도 어셈블리의 클래스로 정의합니다. 각 방법에는 고유한 장점과 단점이 있습니다.  
  
- 클래스 라이브러리를 만드는 경우 사용자 지정 클래스를 서로 다른 여러 애플리케이션에서 공유할 수 있다는 장점이 있습니다. 또한 별도 라이브러리 애플리케이션의 버전 관리 문제를 더 쉽게 컨트롤하고 클래스를 XAML 페이지의 루트 요소로 사용하는 클래스를 간단하게 만들 수 있습니다.  
  
- 사용자 지정 클래스를 애플리케이션에 정의하는 방법은 비교적 간단하며 기본 애플리케이션 실행 파일이 아닌 별도의 어셈블리를 사용할 때 발생하는 배포 및 테스트 문제를 최소화할 수 있다는 장점이 있습니다.  
  
- 동일한 어셈블리에 정의되어 있는지 다른 어셈블리에 정의되어 있는지에 상관없이, 사용자 지정 클래스를 XAML에서 요소로 사용하려면 CLR 네임스페이스와 XML 네임스페이스 간에 매핑해야 합니다. [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)을 참조하세요.  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>사용자 지정 클래스를 XAML 요소로 사용하기 위한 요구 사항  
 클래스를 개체 요소로 인스턴스화하려면 클래스가 다음 요구 사항을 충족해야 합니다.  
  
- 사용자 지정 클래스가 공용 클래스여야 하고 매개 변수가 없는 기본 공용 생성자를 지원해야 합니다. 구조체에 대한 자세한 내용은 다음 섹션을 참조하세요.  
  
- 사용자 지정 클래스가 중첩 클래스가 아니어야 합니다. 중첩 클래스 및 일반 CLR 사용 구문의 "점"은 연결된 속성과 같은 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및/또는 XAML의 기능을 방해합니다.  
  
 개체 요소 구문을 사용하는 것 외에도 개체 정의에서 해당 개체를 값 형식으로 사용하는 다른 공용 속성에 대해서는 속성 요소 구문을 사용해야 합니다. 그 이유는 이제 개체가 개체 요소로 인스턴스화되어 이러한 속성의 속성 요소 값을 채울 수 있기 때문입니다.  
  
### <a name="structures"></a>구조  
 사용자 지정 유형으로 정의하는 구조체는 항상 에서 XAML에서 생성할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이는 CLR 컴파일러가 모든 속성 값을 기본값으로 초기화하는 구조에 대해 매개 변수 없는 생성자를 암시적으로 만들기 때문입니다. 경우에 따라서는 구조체의 기본 생성 동작 및/또는 개체 요소를 사용하는 것이 바람직하지 않습니다. 구조체가 값을 채우고 개념적으로 공용 구조체로 작동하기 때문일 수 있습니다. 이 경우 포함된 값의 해석이 서로 달라서 어느 속성도 설정할 수 없습니다. 이러한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구조의 예는 <xref:System.Windows.GridLength>. 일반적으로 이러한 구조체는 구조체의 값에 대해 서로 다른 해석이나 모드를 만드는 문자열 규칙을 사용하여 값을 특성 형식으로 표현할 수 있도록 형식 변환기를 구현합니다. 또한 구조는 비매개 변수 생성자에서 코드 생성에 대해 유사한 동작을 노출해야 합니다.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>사용자 지정 클래스의 속성을 XAML 특성으로 사용하기 위한 요구 사항  
 속성은 기본 형식(예: 기본 형식)을 참조하거나 매개 변수 없는 생성자 또는 XAML 프로세서가 액세스할 수 있는 전용 형식 변환기가 있는 형식에 클래스를 사용해야 합니다. CLR XAML 구현에서 XAML 프로세서는 언어 프리미티브에 대한 기본 지원을 통해 <xref:System.ComponentModel.TypeConverterAttribute> 또는 백업 형식 정의의 형식 또는 멤버에 대한 응용 프로그램을 통해 이러한 변환기를 찾습니다.  
  
 또는 속성이 추상 클래스 형식 또는 인터페이스를 참조할 수도 있습니다. 추상 클래스나 인터페이스의 경우에는 XAML 구문 분석 시 해당 인터페이스를 구현하는 실제 클래스 인스턴스로 또는 추상 클래스에서 파생되는 형식의 인스턴스로 속성 값을 채워야 합니다.  
  
 속성을 추상 클래스에서 선언할 수 있지만 해당 속성은 추상 클래스에서 파생되는 실제 클래스에서만 설정될 수 있습니다. 이는 클래스에 대한 개체 요소를 전혀 만들려면 클래스에 대한 공개 매개 변수 없는 생성자가 필요하기 때문입니다.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>TypeConverter 사용 특성 구문  
 클래스 수준에서 전용 특성 사용 형식 변환기를 제공한 경우 적용된 형식 변환을 사용하면 해당 형식을 인스턴스화해야 하는 모든 속성에 특성 구문을 사용할 수 있습니다. 형식 변환기형식의 개체 요소 사용을 활성화하지 않습니다. 해당 형식에 대한 매개 변수 없는 생성자의 존재만 개체 요소 사용을 활성화합니다. 따라서 형식 변환기가 사용하는 속성은 일반적으로 속성 구문에서 사용할 수 없습니다. 단, 형식 자체가 개체 요소 구문도 지원하는 경우는 예외입니다. 한 가지 예외적인 경우로 속성 요소에 문자열을 포함하여 속성 요소 구문을 지정할 수 있습니다. 이 사용은 기본적으로 특성 구문 사용과 동일하며 특성 값의 보다 강력한 공백 처리가 필요 하지 않는 한 이러한 사용은 일반적이지 않습니다. 예를 들어 다음은 문자열을 사용하는 속성 요소를 사용하는 방법을 보여 주며 이는 특성을 사용하는 것과 같습니다.  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 특성 구문이 허용되지만 개체 요소를 포함하는 속성 요소 구문이 XAML을 통해 허용되지 않는 속성의 <xref:System.Windows.Input.Cursor> 예는 형식을 취하는 다양한 속성입니다. <xref:System.Windows.Input.Cursor> 클래스에는 전용 형식 변환기가 <xref:System.Windows.Input.CursorConverter>있지만 매개 변수 없는 생성자가 <xref:System.Windows.FrameworkElement.Cursor%2A> 노출되지 않으므로 실제 <xref:System.Windows.Input.Cursor> 형식이 참조 형식인 경우에도 속성은 특성 구문을 통해서만 설정할 수 있습니다.  
  
### <a name="per-property-type-converters"></a>속성별 형식 변환기  
 또는 속성 자체가 속성 수준에서 형식 변환기를 선언할 수도 있습니다. 이렇게 하면 속성 의 들어오는 문자열 값을 해당 형식에 따라 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 작업에 대한 입력으로 처리하여 속성 형식의 개체를 인라인으로 인스턴스화하는 "미니 언어"를 사용할 수 있습니다. 일반적으로 이 작업은 XAML에서 속성을 설정할 수 있는 유일한 방법이 아니라 편리한 접근자를 제공하기 위해 수행합니다. 그러나 매개 변수 없는 생성자 또는 특성 형식 변환기를 제공하지 않는 기존 CLR 형식을 사용하려는 특성에 형식 변환기를 사용할 수도 있습니다. API의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예는 형식을 취하는 특정 <xref:System.Globalization.CultureInfo> 속성입니다. 이 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이전 버전의 프레임워크에서 <xref:System.Globalization.CultureInfo> 사용된 호환성 및 마이그레이션 시나리오를 더 잘 처리하기 위해 기존 <xref:System.Globalization.CultureInfo> Microsoft .NET Framework 형식을 사용했지만 XAML 속성 값으로 직접 사용할 수 있도록 필요한 생성자 또는 형식 수준 형식 변환을 지원하지 않았습니다.  
  
 따라서 컨트롤 작성자는 XAML을 사용하는 속성을 노출할 때마다 해당 속성에 종속성 속성을 지원하는 방법을 고려해야 합니다. 백업을 사용하여 성능을 향상시킬 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 수 있으므로 XAML 프로세서의 기존 구현을 <xref:System.Windows.DependencyProperty> 사용하는 경우 특히 그렇습니다. 종속성 속성은 XAML 액세스 가능 속성이 제공할 것으로 예상되는 속성 시스템의 기능을 노출합니다. 이러한 기능에는 애니메이션, 데이터 바인딩 및 스타일 지원 등이 포함됩니다. 자세한 내용은 [사용자 지정 종속성 속성](custom-dependency-properties.md) 및 [XAML 로드 및 종속성 속성](xaml-loading-and-dependency-properties.md)을 참조하세요.  
  
### <a name="writing-and-attributing-a-type-converter"></a>형식 변환기 작성 및 특성 설정  
 경우에 따라 속성 형식에 <xref:System.ComponentModel.TypeConverter> 대한 형식 변환을 제공하기 위해 사용자 지정 파생 클래스를 작성해야 합니다. XAML 사용을 지원할 수 있는 형식 변환기를 파생하고 만드는 방법과 을 적용하는 <xref:System.ComponentModel.TypeConverterAttribute>방법에 대한 지침은 [TypeConverters 및 XAML](typeconverters-and-xaml.md)을 참조하십시오.  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>사용자 지정 클래스의 이벤트에 XAML 이벤트 처리기 특성 구문을 사용하기 위한 요구 사항  
 CLR 이벤트로 사용하려면 매개 변수 없는 생성자를 지원하는 클래스또는 파생 클래스에서 이벤트에 액세스할 수 있는 추상 클래스에서 해당 이벤트를 공개 이벤트로 노출해야 합니다. 라우트된 이벤트로 편리하게 사용하려면 CLR 이벤트가 CLR 이벤트 `add` `remove` 시그니처에 대한 처리기를 추가 및 제거하고 해당 처리기를 <xref:System.Windows.UIElement.AddHandler%2A> 및 메서드에 <xref:System.Windows.UIElement.RemoveHandler%2A> 전달하는 명시적 메서드와 메서드를 구현해야 합니다. 이 두 메서드는 이벤트가 연결된 인스턴스의 라우트된 이벤트 처리기 저장소에 처리기를 추가하거나 제거합니다.  
  
> [!NOTE]
> 을 사용하여 <xref:System.Windows.UIElement.AddHandler%2A>라우트된 이벤트에 대해 처리기를 직접 등록하고 라우트된 이벤트를 노출하는 CLR 이벤트를 의도적으로 정의하지 않을 수 있습니다. 이벤트에서 연결 처리기에 대해 XAML 특성 구문을 사용하지 않으며 결과 클래스에서 해당 형식의 기능에 대해 투명도가 떨어지는 XAML 보기를 제공하므로, 이 방법은 일반적으로 권장되지 않습니다.  
  
<a name="Collection_Properties"></a>
## <a name="writing-collection-properties"></a>컬렉션 속성 작성  
 컬렉션 형식을 사용하는 속성에는 컬렉션에 추가할 개체를 지정하는 데 사용할 수 있는 XAML 구문이 있습니다. 이 구문은 다음과 같은 두 가지 중요한 기능을 제공합니다.  
  
- 컬렉션 개체인 개체를 개체 요소 구문에 지정할 필요가 없습니다. 컬렉션 형식을 사용하는 XAML에 속성을 지정할 때마다 컬렉션 형식이 항상 암시적으로 존재합니다.  
  
- 태그에서 컬렉션 속성의 자식 요소는 컬렉션의 멤버로 처리됩니다. 일반적으로 컬렉션 멤버에 대한 코드 액세스는 `Add`와 같은 목록/사전 메서드를 통해 또는 인덱서를 통해 수행됩니다. 하지만 XAML 구문은 메서드나 인덱서를 지원하지 않습니다(예외: XAML 2009는 메서드를 지원할 수 있지만, XAML 2009를 사용하여 가능한 WPF 사용을 제한합니다. [XAML 2009 언어 기능](../../../desktop-wpf/xaml-services/xaml-2009-language-features.md) 참조). 컬렉션은 요소 트리를 구성하는 데 있어 공통된 요구 사항이므로 선언적 XAML에서 이러한 컬렉션을 채우는 데 사용할 몇 가지 방법이 필요합니다. 따라서 컬렉션 속성의 자식 요소는 컬렉션 속성 형식 값인 컬렉션에 추가하여 처리됩니다.  
  
 .NET Framework XAML 서비스 구현과 WPF XAML 프로세서에서 컬렉션 속성을 구성하는 사항에 대한 다음 정의를 사용합니다. 속성의 형식은 다음 중 하나를 구현해야 합니다.  
  
- <xref:System.Collections.IList> 구현  
  
- 구현 <xref:System.Collections.IDictionary> 또는 일반 등가 ().<xref:System.Collections.Generic.IDictionary%602>  
  
- 파생(XAML의 배열에 대한 자세한 내용은 <xref:System.Array> [x:배열 마크업 확장/참조)에서](../../../desktop-wpf/xaml-services/xarray-markup-extension.md)파생됩니다.  
  
- 구현(에 <xref:System.Windows.Markup.IAddChild> 의해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]정의된 인터페이스).  
  
 CLR의 각 형식에는 개체 그래프를 만들 때 XAML 프로세서에서 기본 컬렉션에 항목을 추가하는 데 사용하는 `Add` 메서드가 있습니다.  
  
> [!NOTE]
> XAML 프로세서에서<xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602>컬렉션 검색을 위해 일반 `List` `Dictionary` 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 인터페이스(및)는 지원되지 않습니다. 그러나 <xref:System.Collections.Generic.List%601> 클래스는 <xref:System.Collections.IList> 직접 구현하기 때문에 클래스를 기본 클래스로 <xref:System.Collections.Generic.Dictionary%602> 사용하거나 기본 클래스로 <xref:System.Collections.IDictionary> 사용할 수 있습니다.  
  
 컬렉션을 사용하는 속성을 선언하는 경우 해당 형식의 새 인스턴스에서 속성 값이 초기화되는 방법에 유의하세요. 속성을 종속성 속성으로 구현하지 않는 경우에는 속성이 컬렉션 형식 생성자를 호출하는 지원 필드를 사용하도록 설정하는 것이 좋습니다. 속성이 종속성 속성인 경우에는 기본 형식 생성자의 일부로 컬렉션 속성을 초기화해야 할 수 있습니다. 그 이유는 종속성 속성이 속성의 기본값을 메타데이터에서 가져오는데, 개발자는 일반적으로 컬렉션 속성의 초기 값을 정적 공유 컬렉션에 사용하지 않으려고 하기 때문입니다. 형식 인스턴스를 포함하는 경우마다 컬렉션 인스턴스가 있어야 합니다. 자세한 내용은 [사용자 지정 종속성 속성](custom-dependency-properties.md)을 참조하세요.  
  
 컬렉션 속성에 대해 사용자 지정 컬렉션 형식을 구현할 수 있습니다. 암시적 컬렉션 속성 처리로 인해 사용자 지정 컬렉션 형식은 XAML에서 암시적으로 사용되기 위해 매개 변수 없는 생성기를 제공할 필요가 없습니다. 그러나 선택적으로 컬렉션 형식에 대 한 매개 변수 없는 생성자 제공할 수 있습니다. 이 방법은 유용한 방법입니다. 매개 변수 없는 생성자 제공 하지 않는 한 컬렉션을 개체 요소로 명시적으로 선언할 수 없습니다. 명시적 컬렉션을 태그 스타일의 문제로 보는 태그 작성자도 있습니다. 또한 매개 변수 없는 생성자는 컬렉션 형식을 속성 값으로 사용하는 새 개체를 만들 때 초기화 요구 사항을 단순화할 수 있습니다.  
  
<a name="XAMLCONtent"></a>
## <a name="declaring-xaml-content-properties"></a>XAML 콘텐츠 속성 선언  
 XAML 언어를 통해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 콘텐츠 속성의 개념을 정의합니다. 개체 구문에서 사용할 수 있는 각 클래스에는 정확히 하나의 XAML 콘텐츠 속성만 포함될 수 있습니다. 클래스의 XAML 콘텐츠 속성으로 속성을 선언하려면 클래스 <xref:System.Windows.Markup.ContentPropertyAttribute> 정의의 일부로 적용합니다. 의도한 XAML 콘텐츠 속성의 이름을 <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> 특성의 이름으로 지정합니다. 속성은 의 리플렉션 구문으로 지정되지 <xref:System.Reflection.PropertyInfo>않고 이름으로 문자열로 지정됩니다.  
  
 컬렉션 속성을 XAML 콘텐츠 속성으로 지정할 수 있습니다. 이 경우 중간의 컬렉션 개체 요소나 속성 요소 태그 없이도 개체 요소가 하나 이상의 자식 요소를 가질 수 있는 상황에서 해당 속성이 사용됩니다. 그러면 이러한 요소가 XAML 콘텐츠 속성에 대한 값으로 처리되어 지원 컬렉션 인스턴스에 추가됩니다.  
  
 기존 XAML 콘텐츠 속성 중 일부에서는 `Object`의 속성 형식을 사용합니다. 이렇게 하면 <xref:System.String> A와 같은 기본 값을 취할 수 있는 XAML 콘텐츠 속성뿐만 아니라 단일 참조 개체 값을 사용할 수 있습니다. 이 모델을 따르는 경우 사용자의 형식을 통해 형식을 결정하고 가능한 형식을 처리합니다. 콘텐츠 형식의 <xref:System.Object> 일반적인 이유는 기본 프레젠테이션 처리를 받는 문자열로 개체 콘텐츠를 추가하는 간단한 방법 또는 기본이 아닌 프레젠테이션 또는 추가 데이터를 지정하는 고급 개체 콘텐츠를 추가하는 고급 수단을 모두 지원하기 위해서입니다.  
  
<a name="Serializing"></a>
## <a name="serializing-xaml"></a>XAML Serialize  
 예를 들어 컨트롤 작성자인 경우 XAML에서 인스턴스화할 수 있는 개체 표현도 해당 XAML 태그로 다시 serialize할 수 있도록 하려는 경우가 있습니다. Serialization 요구 사항은 이 항목에서 설명하지 않습니다. [컨트롤 작성 개요](../controls/control-authoring-overview.md) 및 [요소 트리 및 Serialization](element-tree-and-serialization.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
- [기본 요소 개요](base-elements-overview.md)
- [XAML 로드 및 종속성 속성](xaml-loading-and-dependency-properties.md)
