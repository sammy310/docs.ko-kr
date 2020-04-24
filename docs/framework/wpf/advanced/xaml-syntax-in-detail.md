---
title: XAML 구문 정보
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
ms.openlocfilehash: 5f8bb862ce443fd7397036b10f69cda65a6960bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646153"
---
# <a name="xaml-syntax-in-detail"></a>XAML 구문 정보
이 항목에서는 XAML 구문의 요소를 설명하는 데 사용되는 용어를 정의합니다. 이러한 용어는 WPF 설명서와 XAML을 사용하는 다른 프레임워크 또는 System.Xaml 수준에서 XAML 언어 지원에서 사용할 수 있는 기본 XAML 개념모두에 대해 이 설명서의 나머지 부분에서 자주 사용됩니다. 이 항목에서는 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)항목에 소개된 기본 용어에 대해 확장합니다.  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>XAML 언어 사양  
 여기에 정의된 XAML 구문 용어도 XAML 언어 사양 내에서 정의또는 참조됩니다. XAML은 XML을 기반으로 하는 언어이며 XML 구조 규칙을 따르거나 확장합니다. 일부 용어는 XML 언어 또는 XML 문서 개체 모델을 설명할 때 일반적으로 사용되는 용어에서 공유되거나 기반으로 합니다.  
  
 XAML 언어 사양에 대한 자세한 내용은 Microsoft 다운로드 센터에서 [ \[MS-XAML을\] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf) 다운로드하십시오.  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML 및 CLR  
 XAML은 태그 언어입니다. 공통 언어 런타임(CLR)은 이름에서 암시하는 것처럼 런타임 실행을 가능하게 합니다. XAML은 자체적으로 CLR 런타임에서 직접 사용하는 공통 언어 중 하나가 아닙니다. 대신 XAML을 자체 형식 시스템을 지원하는 것으로 생각할 수 있습니다. WPF에서 사용하는 특정 XAML 구문 분석 시스템은 CLR 및 CLR 형식 시스템에 빌드됩니다. XAML 형식은 WPF에 대한 XAML이 구문 분석될 때 런타임 표현을 인스턴스화하기 위해 CLR 형식에 매핑됩니다. 이러한 이유로 이 문서의 구문에 대한 나머지 토론에는 XAML 언어 사양의 동등한 구문 설명이 적용되지 않더라도 CLR 형식 시스템에 대한 참조가 포함됩니다. XAML 언어 사양 수준에 따라 XAML 형식은 CLR일 필요는 없지만 다른 XAML 파서를 만들고 사용해야 하는 다른 형식 시스템에 매핑될 수 있습니다.  
  
#### <a name="members-of-types-and-class-inheritance"></a>형식 및 클래스 상속의 구성원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식의 XAML 멤버로 표시되는 속성 및 이벤트는 종종 기본 형식에서 상속됩니다. 예를 들어 이 예제를 고려합니다. `<Button Background="Blue" .../>` 클래스 <xref:System.Windows.Controls.Control.Background%2A> 정의, 반사 결과 또는 <xref:System.Windows.Controls.Button> 설명서를 살펴보면 속성이 클래스에서 즉시 선언된 속성이 아닙니다. 대신 <xref:System.Windows.Controls.Control.Background%2A> 기본 <xref:System.Windows.Controls.Control> 클래스에서 상속됩니다.  
  
 XAML 요소의 클래스 상속 동작은 XML 태그의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스키마 적용 해석에서 중요한 출발점입니다. 클래스 상속은 특히 중간 기본 클래스가 추상적이거나 인터페이스가 관련된 경우 복잡해질 수 있습니다. 이는 XAML 요소 집합과 허용 가능한 특성 집합이 일반적으로 DTD 또는 XSD 형식과 같은 XML 프로그래밍에 사용되는 스키마 형식을 사용하여 정확하고 완전하게 표현하기 어려운 이유 중 하나입니다. 또 다른 이유는 XAML 언어 자체의 확장성 및 형식 매핑 기능이 허용 형식 및 멤버의 고정 된 표현의 완전성을 배제하기 때문입니다.  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>개체 요소 구문  
 *개체 요소 구문은* XML 요소를 선언하여 CLR 클래스 또는 구조를 인스턴스화하는 XAML 태그 구문입니다. 이 구문은 HTML과 같은 다른 태그 언어의 요소 구문과 유사합니다. 개체 요소 구문은 왼쪽 각도\<대괄호()로 시작하여 인스턴스화되는 클래스 또는 구조체의 형식 이름바로 다음에 시작합니다. 0 개 이상의 공백은 형식 이름을 따를 수 있으며, 각 특성 name="value" 쌍을 구분하는 하나 이상의 공백을 통해 개체 요소에 0 개 이상의 특성이 선언될 수도 있습니다. 마지막으로 다음 중 하나가 true여야 합니다.  
  
- 요소와 태그는 정방향 슬래시(/)로 닫아야 하며 직각 대괄호(>)가 바로 뒤에 있어야 합니다.  
  
- 개구부 태그는 직각 브래킷(>)으로 완료되어야 합니다. 다른 오브젝트 요소, 속성 요소 또는 내부 텍스트는 여는 태그를 따를 수 있습니다. 여기에 포함될 수 있는 콘텐츠는 일반적으로 요소의 개체 모델에 의해 제한됩니다. 객체 요소에 대한 동등한 닫는 태그도 적절한 중첩 및 다른 열기 및 닫기 태그 쌍과 균형을 유지해야 합니다.  
  
 .NET에서 구현한 XAML에는 개체 요소를 형식으로 매핑하고 속성 또는 이벤트에 대한 속성, XAML 네임스페이스를 CLR 네임스페이스와 어셈블리에 매핑하는 규칙 집합이 있습니다. WPF 및 .NET의 경우 XAML 개체 요소는 참조된 어셈블리에 정의된 대로 .NET 형식에 매핑되고 특성은 해당 형식의 멤버에 매핑됩니다. XAML에서 CLR 형식을 참조하면 해당 형식의 상속된 멤버에도 액세스할 수 있습니다.  
  
 예를 들어 다음 예제는 <xref:System.Windows.Controls.Button> 클래스의 새 인스턴스를 인스턴스화하 고 해당 특성에 대 <xref:System.Windows.FrameworkElement.Name%2A> 한 특성 및 값을 지정 하는 개체 요소 구문입니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 다음 예제는 XAML 콘텐츠 속성 구문도 포함하는 개체 요소 구문입니다. 내에 포함된 내부 텍스트는 <xref:System.Windows.Controls.TextBox> XAML 콘텐츠 속성을 <xref:System.Windows.Controls.TextBox.Text%2A>설정하는 데 사용됩니다.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>콘텐츠 모델  
 클래스는 구문 측면에서 XAML 개체 요소로 사용을 지원할 수 있지만 해당 요소는 전체 콘텐츠 모델 또는 요소 트리의 예상 위치에 배치될 때만 응용 프로그램이나 페이지에서 제대로 작동합니다. 예를 들어 <xref:System.Windows.Controls.MenuItem> a는 일반적으로 와 같은 <xref:System.Windows.Controls.Primitives.MenuBase> <xref:System.Windows.Controls.Menu>파생 클래스의 자식으로만 배치되어야 합니다. 특정 요소에 대한 콘텐츠 모델은 XAML 요소로 사용할 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 있는 컨트롤 및 기타 클래스에 대한 클래스 페이지의 설명의 일부로 문서화됩니다.  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>개체 요소의 속성  
 XAML의 속성은 다양한 가능한 구문으로 설정됩니다. 특정 속성에 사용할 수 있는 구문은 설정하는 속성의 기본 형식 시스템 특성에 따라 달라집니다.  
  
 속성 값을 설정하면 런타임 개체 그래프에 있는 객체에 피처 또는 특성을 추가할 수 있습니다. 개체 요소에서 생성된 개체의 초기 상태는 매개 변수 없는 생성자 동작을 기반으로 합니다. 일반적으로 응용 프로그램은 지정된 개체의 완전히 기본 인스턴스가 아닌 다른 것을 사용합니다.  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>특성 구문(속성)  
 특성 구문은 기존 개체 요소에 특성을 선언하여 속성에 대한 값을 설정하는 XAML 태그 구문입니다. 특성 이름은 관련 개체 요소를 백업하는 클래스의 속성의 CLR 멤버 이름과 일치해야 합니다. 특성 이름 뒤에 할당 연산자(=)가 표시됩니다. 특성 값은 따옴표 내에 둘러싸인 문자열이어야 합니다.  
  
> [!NOTE]
> 번갈아 따옴표를 사용하여 특성 내에 리터럴 따옴표를 배치할 수 있습니다. 예를 들어, 단일 따옴표를 수단으로 사용하여 그 안에 double quote 문자가 포함된 문자열을 선언할 수 있습니다. 단일 따옴표또는 큰따옴표를 사용하든 속성 값 문자열을 열고 닫을 때 일치하는 쌍을 사용해야 합니다. 또한 이스케이프 시퀀스 또는 특정 XAML 구문에 의해 부과 된 문자 제한을 해결 하는 데 사용할 수 있는 다른 기술도 있습니다. [XML 문자 엔터티 및 XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md)을 참조하십시오.  
  
 특성 구문을 통해 설정하려면 속성이 공용이어야 하며 작성가능해야 합니다. 백킹 형식 시스템의 속성 값은 값 형식이거나 관련 백업 형식에 액세스할 때 XAML 프로세서에서 인스턴스화하거나 참조할 수 있는 참조 유형이어야 합니다.  
  
 WPF XAML 이벤트의 경우 특성 이름으로 참조되는 이벤트는 공용이어야 하며 공용 대리자가 있어야 합니다.  
  
 속성 또는 이벤트는 포함된 개체 요소에 의해 인스턴스화되는 클래스 또는 구조체의 멤버여야 합니다.  
  
### <a name="processing-of-attribute-values"></a>특성 값 처리  
 개폐 견적 부호에 포함된 문자열 값은 XAML 프로세서에서 처리됩니다. 속성의 경우 기본 처리 동작은 기본 CLR 속성의 유형에 의해 결정됩니다.  
  
 특성 값은 다음 중 하나로 채워지며 이 처리 순서를 사용합니다.  
  
1. XAML 프로세서가 "중괄호" 또는 에서 <xref:System.Windows.Markup.MarkupExtension>파생되는 개체 요소가 발생하는 경우 참조된 태그 확장은 값을 문자열로 처리하는 대신 먼저 평가되고 태그 확장에서 반환되는 개체가 값으로 사용됩니다. 대부분의 경우 태그 확장으로 반환되는 개체는 기존 개체에 대한 참조또는 런타임까지 평가를 연기하고 새로 인스턴스화된 개체가 아닌 식입니다.  
  
2. 속성이 <xref:System.ComponentModel.TypeConverter>특성으로 선언되거나 해당 속성의 값 형식이 특성으로 <xref:System.ComponentModel.TypeConverter>선언되면 특성의 문자열 값이 변환 입력으로 형식 변환기변환에 제출되고 변환기가 새 개체 인스턴스를 반환합니다.  
  
3. <xref:System.ComponentModel.TypeConverter>이 없음이 있으면 속성 유형에 대한 직접 변환이 시도됩니다. 이 최종 수준은 XAML 언어 기본 형식 간의 파서 네이티브 값으로 직접 변환하거나 열거형에서 명명된 상수의 이름을 검사합니다(파서는 일치하는 값에 액세스함).  
  
#### <a name="enumeration-attribute-values"></a>열거 특성 값  
 XAML의 열거는 XAML 구문 분석자에 의해 본질적으로 처리되며 열거형의 멤버는 열거형의 명명된 상수 중 하나의 문자열 이름을 지정하여 지정해야 합니다.  
  
 비플래그 열거 값의 경우 네이티브 동작은 특성 값의 문자열을 처리하고 열거형 값 중 하나로 해결하는 것입니다. *열거형*열거형에 열거형은 지정하지 않습니다. *값*, 코드에서와 마찬가지로. 대신 *값만*지정하고 *열거형은* 설정하는 속성의 유형에 의해 유추됩니다. *열거형*에서 특성을 지정하는 경우 . *값* 양식, 그것은 제대로 해결 되지 않습니다.  
  
 플래그 별 열거형의 경우 동작은 <xref:System.Enum.Parse%2A?displayProperty=nameWithType> 메서드를 기반으로 합니다. 각 값을 쉼표로 구분하여 플래그 구분 열거형에 대해 여러 값을 지정할 수 있습니다. 그러나 플래그가 없는 열거형 값을 결합할 수는 없습니다. 예를 들어 쉼표 구문을 사용하여 플래그가 없는 <xref:System.Windows.Trigger> 열거형의 여러 조건에서 작동하는 a를 만들 수 없습니다.  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 XAML에서 설정할 수 있는 특성을 지원하는 플래그와이즈 열거형은 WPF에서 드뭅니다. 그러나 이러한 열거형 중 <xref:System.Windows.Media.StyleSimulations>하나입니다. 예를 들어 쉼표구분 플래그와이즈 특성 구문을 사용하여 클래스에 대한 설명에 제공된 <xref:System.Windows.Documents.Glyphs> 예제를 수정할 수 있습니다. `StyleSimulations = "BoldSimulation"` 될 `StyleSimulations = "BoldSimulation,ItalicSimulation"`수 있습니다. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>은 두 개 이상의 열거 값을 지정할 수 있는 또 다른 속성입니다. 그러나 <xref:System.Windows.Input.ModifierKeys> 열거형은 자체 형식 변환기를 지원하므로 이 속성은 특별한 경우입니다. 수정자에 대한 형식 변환기는 쉼표(,)가 아닌 구분기호로 더하기 기호(+)를 사용합니다. 이 변환은 "Ctrl+Alt"와 같은 Microsoft Windows 프로그래밍의 주요 조합을 나타내는 보다 전통적인 구문을 지원합니다.  
  
### <a name="properties-and-event-member-name-references"></a>속성 및 이벤트 멤버 이름 참조  
 특성을 지정할 때 포함된 개체 요소에 대해 인스턴스화한 CLR 형식의 멤버로 존재하는 모든 속성 또는 이벤트를 참조할 수 있습니다.  
  
 또는 포함된 개체 요소와 관계없이 연결된 속성 또는 연결된 이벤트를 참조할 수 있습니다. 첨부된 속성은 다음 섹션에서 설명합니다.  
  
 *typeName*을 사용하여 기본 네임스페이스를 통해 액세스할 수 있는 모든 개체의 이벤트 이름을 지정할 수도 있습니다. *이벤트* 부분적으로 정규화된 이름; 이 구문은 처리기가 자식 요소에서 이벤트 라우팅을 처리하기 위한 라우트된 이벤트에 대한 처리기를 첨부하는 것을 지원하지만 부모 요소는 해당 멤버 테이블에 해당 이벤트가 없습니다. 이 구문은 연결된 이벤트 구문과 유사하지만 여기서 이벤트는 실제 연결된 이벤트가 아닙니다. 대신 정규화된 이름으로 이벤트를 참조합니다. 자세한 내용은 [라우트된 이벤트 개요](routed-events-overview.md)합니다.  
  
 일부 시나리오에서는 속성 이름이 특성 이름이 아니라 특성 값으로 제공되는 경우도 있습니다. 해당 속성 이름에는 양식 *ownerType에*지정된 속성과 같은 한정자도 포함될 수 있습니다. *종속성속성 Name*. 이 시나리오는 XAML에서 스타일이나 템플릿을 작성할 때 일반적입니다. 속성 값으로 제공되는 속성 이름에 대한 처리 규칙은 서로 다르며 설정되는 속성의 형식 또는 특정 WPF 하위 시스템의 동작에 의해 제어됩니다. 자세한 내용은 [스타일 지정 및 템플릿을](../../../desktop-wpf/fundamentals/styles-templates-overview.md)참조하십시오.  
  
 속성 이름에 대한 또 다른 용도는 특성 값이 속성-속성 관계를 설명하는 경우입니다. 이 기능은 데이터 바인딩 및 스토리보드 대상에 사용되며 <xref:System.Windows.PropertyPath> 클래스 및 해당 형식 변환기에서 사용할 수 있습니다. 조회 의미체계에 대한 자세한 설명은 [PropertyPath XAML 구문을](propertypath-xaml-syntax.md)참조하십시오.  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>속성 요소 구문  
 *속성 요소 구문은* 요소에 대한 기본 XML 구문 규칙과 다소 다른 구문입니다. XML에서 특성값은 사실상 문자열이며, 가능한 유일한 변형은 사용 중인 문자열 인코딩 형식입니다. XAML에서 다른 개체 요소를 속성값으로 지정할 수 있습니다. 이 기능은 속성 요소 구문에서 사용할 수 있습니다. 속성이 요소 태그 내에서 특성으로 지정되는 대신 *elementType Name에서*여는 요소 태그를 사용하여 속성이 지정됩니다. *propertyName* 양식, 속성의 값이 내에 지정 된 다음 속성 요소가 닫힙니다.  
  
 특히 구문은 왼쪽 각도 대괄호\<()로 시작하여 속성 요소 구문이 포함된 클래스 또는 구조체의 형식 이름바로 다음에 표시됩니다. 그 다음에는 단일 점(.) 다음에 속성 이름, 직각 대괄호(>)가 바로 뒤에 표시됩니다. 특성 구문과 마찬가지로 해당 속성은 지정된 형식의 선언된 공용 멤버 내에 있어야 합니다. 속성에 할당할 값은 속성 요소 내에 포함됩니다. 일반적으로 개체를 값으로 지정하는 것은 속성 요소 구문이 해결하려는 시나리오이기 때문에 값이 하나 이상의 개체 요소로 지정됩니다. 마지막으로 동일한 요소를 지정하는 동일한 닫는 *태그TypeName*. *propertyName* 조합은 적절한 중첩 및 다른 요소 태그와 균형을 제공해야합니다.  
  
 예를 들어 다음은 <xref:System.Windows.FrameworkElement.ContextMenu%2A> <xref:System.Windows.Controls.Button>의 속성에 대한 속성 요소 구문입니다.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 속성 요소 내의 값은 지정되는 속성 형식이 <xref:System.String>기본 값 유형(예: ) 또는 이름이 지정된 열거형인 경우 내부 텍스트로 지정될 수도 있습니다. 이러한 두 가지 사용법은 각각더 간단한 특성 구문을 사용할 수도 있기 때문에 다소 드물다. 속성 요소를 문자열로 채우는 한 가지 시나리오는 XAML 콘텐츠 속성이 아니지만 UI 텍스트를 표현하는 데 여전히 사용되는 속성에 대한 것이며, 라인 피드와 같은 특정 공백 요소는 해당 UI 텍스트에 나타나야 합니다. 특성 구문은 줄 바수를 보존할 수 없지만 속성 요소 구문은 상당한 공백 보존이 활성화되어 있는 한(자세한 내용은 [XAML의 공백 처리](../../../desktop-wpf/xaml-services/white-space-processing.md)참조). 또 다른 시나리오는 [x:Uid Directive가](../../../desktop-wpf/xaml-services/xuid-directive.md) 속성 요소에 적용되어 WPF 출력 BAML 또는 다른 기술에 지역화되어야 하는 값으로 표시할 수 있도록 하는 것입니다.  
  
 속성 요소는 WPF 논리 트리에 표시되지 않습니다. 속성 요소는 속성을 설정하기 위한 특정 구문일 뿐이며 속성을 백업하는 인스턴스 나 개체가 있는 요소가 아닙니다. 논리 트리 개념에 대한 자세한 내용은 [WPF의 트리를](trees-in-wpf.md)참조하십시오.  
  
 특성 및 속성 요소 구문이 모두 지원되는 속성의 경우 공백 처리와 같은 미묘한 내용은 구문마다 약간 다를 수 있지만 두 구문은 일반적으로 동일한 결과를 갖습니다.  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>컬렉션 구문  
 XAML 사양에서는 값 형식이 컬렉션인 속성을 식별하기 위해 XAML 프로세서 구현이 필요합니다. .NET의 일반적인 XAML 프로세서 구현은 관리 코드와 CLR을 기반으로 하며 다음 중 하나를 통해 컬렉션 형식을 식별합니다.  
  
- 형식 구현 <xref:System.Collections.IList>.  
  
- 형식 구현 <xref:System.Collections.IDictionary>.  
  
- 형식 <xref:System.Array> 파생(XAML의 배열에 대한 자세한 내용은 [x:배열 마크업 확장을](../../../desktop-wpf/xaml-services/xarray-markup-extension.md)참조하십시오.)  
  
 속성의 형식이 컬렉션인 경우 유추된 컬렉션 형식을 태그에 개체 요소로 지정할 필요가 없습니다. 대신 컬렉션의 항목으로 지정되는 요소는 속성 요소의 하나 이상의 자식 요소로 지정됩니다. 이러한 각 항목은 로드 하는 동안 개체에 대 한 `Add` 평가 하 고 암시된 컬렉션의 메서드를 호출 하 여 컬렉션에 추가 됩니다. 예를 들어, <xref:System.Windows.Style.Triggers%2A> 의 <xref:System.Windows.Style> 속성은 구현 <xref:System.Windows.TriggerCollection>하는 특수 <xref:System.Collections.IList>컬렉션 형식을 걸립니다. 태그에서 <xref:System.Windows.TriggerCollection> 개체 요소를 인스턴스화할 필요는 없습니다. <xref:System.Windows.Trigger> 대신 하나 이상의 항목을 속성 요소 `Style.Triggers` 내의 요소로 지정하는 경우(또는 <xref:System.Windows.Trigger> 파생 클래스)는 강하게 형식화되고 암시적 <xref:System.Windows.TriggerCollection>에 대한 항목 유형으로 예상되는 형식입니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 속성은 컬렉션 형식과 해당 형식 및 파생 형식에 대한 XAML 콘텐츠 속성일 수 있으며 이 항목의 다음 섹션에서 설명합니다.  
  
 암시적 컬렉션 요소는 태그에 요소로 나타나지 않더라도 논리 트리 표현에서 멤버를 만듭니다. 일반적으로 부모 형식의 생성자는 해당 속성 중 하나인 컬렉션에 대한 인스턴스화를 수행하며 처음 비어 있는 컬렉션은 개체 트리의 일부가 됩니다.  
  
> [!NOTE]
> 제네릭 목록 및<xref:System.Collections.Generic.IList%601> 사전 <xref:System.Collections.Generic.IDictionary%602>인터페이스(및)는 컬렉션 검색에 지원되지 않습니다. 그러나 <xref:System.Collections.Generic.List%601> 클래스는 <xref:System.Collections.IList> 직접 구현하기 때문에 클래스를 기본 클래스로 <xref:System.Collections.Generic.Dictionary%602> 사용하거나 기본 클래스로 <xref:System.Collections.IDictionary> 사용할 수 있습니다.  
  
 컬렉션 형식에 대 한 .NET 참조 페이지에서 컬렉션에 대 한 개체 요소를 의도적으로 생략 하는이 구문은 경우에 따라 XAML 구문 섹션에 암시적 컬렉션 구문으로 기록 됩니다.  
  
 루트 요소를 제외하고 다른 요소의 자식 요소로 중첩된 XAML 파일의 모든 개체 요소는 실제로 부모 요소의 암시적 컬렉션 속성의 멤버 또는 상위 요소에 대한 XAML 콘텐츠 속성의 값을 지정하는 요소(XAML 콘텐츠 속성은 다음 섹션에서 설명)와 같은 경우 중 하나 또는 둘 모두에 해당하는 요소입니다. 즉, 태그 페이지의 부모 요소와 자식 요소의 관계는 실제로 루트의 단일 개체이며 루트 아래의 모든 개체 요소는 부모의 속성 값을 제공하는 단일 인스턴스이거나 컬렉션 내의 항목 중 하나이며 부모의 컬렉션 형식 속성 값입니다. 이 단일 루트 개념은 XML에서 일반적이며 와 같은 <xref:System.Windows.Markup.XamlReader.Load%2A>XAML을 로드하는 API 동작에서 자주 강화됩니다.  
  
 다음 예제는 컬렉션 ()<xref:System.Windows.Media.GradientStopCollection>명시적으로 지정 된 개체 요소와 구문입니다.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 컬렉션을 명시적으로 선언하는 것이 항상 가능한 것은 아닙니다. 예를 들어 이전에 <xref:System.Windows.TriggerCollection> 보여 지는 <xref:System.Windows.Style.Triggers%2A> 예제에서 명시적으로 선언하려고 하면 실패합니다. 컬렉션을 명시적으로 선언하려면 컬렉션 클래스가 매개 변수 없는 생성자(parameterless 생성자)를 지원해야 하며 <xref:System.Windows.TriggerCollection> 매개 변수 없는 생성자가 없어야 합니다.  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>XAML 콘텐츠 속성  
 XAML 콘텐츠 구문은 해당 클래스 선언의 일부로 를 <xref:System.Windows.Markup.ContentPropertyAttribute> 지정하는 클래스에서만 활성화되는 구문입니다. 파생 <xref:System.Windows.Markup.ContentPropertyAttribute> 클래스를 포함하여 해당 요소 형식의 콘텐츠 속성인 속성 이름을 참조합니다. XAML 프로세서에서 처리하면 개체 요소의 열기 및 닫기 태그 사이에 있는 자식 요소 또는 내부 텍스트가 해당 개체에 대한 XAML 콘텐츠 속성값으로 할당됩니다. content 속성에 대한 명시적 속성 요소를 지정할 수 있지만 이 사용법은 일반적으로 .NET 참조의 XAML 구문 섹션에 표시되지 않습니다. 명시적/자세한 기술은 태그 명확성 또는 태그 스타일에 대한 가끔 값을 가지지만 일반적으로 콘텐츠 속성의 의도는 부모 자식으로 직관적으로 관련된 요소를 직접 중첩할 수 있도록 태그를 간소화하는 것입니다. 요소의 다른 속성에 대한 속성 요소 태그는 엄격한 XAML 언어 정의에 따라 "콘텐츠"로 할당되지 않습니다. 이전에XAML 파서의 처리 순서에서 처리되었으며 "콘텐츠"로 간주되지 않습니다.  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML 콘텐츠 속성 값은 연속적이어야 합니다.  
 XAML 콘텐츠 속성의 값은 해당 개체 요소의 다른 속성 요소 이전 또는 전적으로 제공되어야 합니다. 이는 XAML 콘텐츠 속성의 값이 문자열로 지정되든 하나 이상의 개체로 지정되는지 여부에 관계없이 마찬가지입니다. 예를 들어 다음 태그는 구문 분석하지 않습니다.  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 이 구문이 콘텐츠 속성에 대 한 속성 요소 구문을 사용 하 여 명시적으로 만든 경우 콘텐츠 속성 두 번 설정 됩니다 때문에 기본적으로 불법 입니다.  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 마찬가지로 불법적인 예는 content 속성이 컬렉션이고 자식 요소가 속성 요소와 함께 산재되어 있는 경우입니다.  
  
```xaml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>
## <a name="content-properties-and-collection-syntax-combined"></a>콘텐츠 속성 및 컬렉션 구문 조합  
 두 개 이상의 개체 요소를 콘텐츠로 허용하려면 콘텐츠 속성의 형식이 컬렉션 형식이어야 합니다. 컬렉션 형식에 대 한 속성 요소 구문과 마찬가지로 XAML 프로세서는 컬렉션 형식인 형식을 식별 해야 합니다. 요소에 XAML 콘텐츠 속성이 있고 XAML 콘텐츠 속성의 형식이 컬렉션인 경우 암시된 컬렉션 형식을 태그에 개체 요소로 지정할 필요가 없으며 XAML 콘텐츠 속성을 속성 요소로 지정할 필요가 없습니다. 따라서 태그의 명백한 콘텐츠 모델에는 콘텐츠로 할당된 두 개 이상의 자식 요소가 있을 수 있습니다. 다음은 파생 클래스의 콘텐츠 <xref:System.Windows.Controls.Panel> 구문입니다. 파생된 모든 <xref:System.Windows.Controls.Panel> 클래스는 XAML <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.UIElementCollection>콘텐츠 속성을 type 값이어야 하는 것으로 설정합니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 태그에는 에 대한 <xref:System.Windows.Controls.Panel.Children%2A> 속성 요소나 <xref:System.Windows.Controls.UIElementCollection> 에 대한 요소가 필요하지 않습니다. 이 기능은 A를 정의하는 재귀적으로 포함된 요소가 속성 요소 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 태그 나 컬렉션 개체를 개입하지 않고 즉시 부모-자식 요소 관계가 있는 중첩 요소 트리로 보다 직관적으로 표현되도록 XAML의 디자인 기능입니다. 실제로 의도적으로 <xref:System.Windows.Controls.UIElementCollection> 태그에 개체 요소로 명시적으로 지정할 수 없습니다. 의도된 용도만 암시적 컬렉션이므로 <xref:System.Windows.Controls.UIElementCollection> public parameterless 생성자가 노출되지 않으므로 개체 요소로 인스턴스화할 수 없습니다.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>콘텐츠 속성과 개체의 속성 요소 및 개체 요소 혼합  
 XAML 사양은 XAML 프로세서가 개체 요소 내에서 XAML 콘텐츠 속성을 채우는 데 사용되는 개체 요소를 연속적이어야 하며 혼합해서는 안 된다는 것을 선언합니다. 특성 요소 및 콘텐츠 혼합에 대한 이러한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제한은 XAML 프로세서에 의해 적용됩니다.  
  
 개체 요소 내에서 첫 번째 즉각적인 태그로 자식 개체 요소를 가질 수 있습니다. 그런 다음 속성 요소를 소개할 수 있습니다. 또는 하나 이상의 속성 요소를 지정한 다음 콘텐츠를 지정한 다음 더 많은 속성 요소를 지정할 수 있습니다. 그러나 속성 요소가 콘텐츠를 따라오면 더 이상 콘텐츠를 도입할 수 없으며 속성 요소만 추가할 수 있습니다.  
  
 이 콘텐츠/속성 요소 순서 요구 사항은 콘텐츠로 사용되는 내부 텍스트에는 적용되지 않습니다. 그러나 속성 요소가 내부 텍스트와 산재된 경우 중요한 공백이 태그에서 시각적으로 감지하기 어렵기 때문에 내부 텍스트를 연속적으로 유지하는 것이 좋습니다.  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>XAML 네임스페이스  
 앞의 구문 예제 중 어느 것도 기본 XAML 네임스페이스 이외의 XAML 네임스페이스를 지정하지 않았습니다. 일반적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 기본 XAML 네임스페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 네임스페이스로 지정됩니다. 기본 XAML 네임스페이스 이외의 XAML 네임스페이스를 지정하고 유사한 구문을 계속 사용할 수 있습니다. 그러나 기본 XAML 네임스페이스 내에서 액세스할 수 없는 클래스의 이름이 지정된 모든 곳에서 해당 클래스 이름 앞에 해당 CLR 네임스페이스에 매핑된 XAML 네임스페이스의 접두사 앞에 있어야 합니다. 예를 `<custom:Example/>` `Example` 들어, 해당 클래스를 포함하는 CLR 네임스페이스(및 백업 형식을 포함하는 외부 어셈블리 정보)가 이전에 접두사에 매핑된 `custom` 클래스의 인스턴스를 인스턴스화하는 개체 요소 구문입니다.  
  
 XAML 네임스페이스에 대한 자세한 내용은 [XAML 네임스페이스 및 WPF XAML에 대한 네임스페이스 매핑을](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조하십시오.  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>태그 확장  
 XAML은 문자열 특성 값 또는 개체 요소의 일반 XAML 프로세서 처리에서 이스케이프를 가능하게 하고 백업 클래스로 처리를 연기하는 태그 확장 프로그래밍 엔터티를 정의합니다. 특성 구문을 사용할 때 XAML 프로세서에 대한 태그 확장을 식별하는 문자는 열기 중괄호({)이며 닫는 곱슬 대괄호(})가 아닌 다른 문자가 뒤따릅니다. 여는 곱슬 대괄호 다음의 첫 번째 문자열은 특정 확장 동작을 제공하는 클래스를 참조해야 하며, 여기서 해당 하위 문자열이 실제 클래스 이름의 일부인 경우 참조가 하위 문자열 "Extension"을 생략할 수 있습니다. 그 후 단일 공백이 나타날 수 있으며, 닫는 곱슬 대괄호가 발생할 때까지 각 후속 문자는 확장 구현에 의해 입력으로 사용됩니다.  
  
 .NET XAML 구현에서는 <xref:System.Windows.Markup.MarkupExtension> 추상 클래스를 다른 프레임워크 나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술뿐만 아니라 지원하는 모든 태그 확장의 기준으로 사용합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 특별히 구현하는 태그 확장은 종종 다른 기존 개체를 참조하거나 런타임에 평가될 객체에 대한 지연된 참조를 만들기 위한 것입니다. 예를 들어 간단한 WPF 데이터 바인딩은 특정 `{Binding}` 속성이 일반적으로 수행하는 값 대신 태그 확장을 지정하여 수행됩니다. 대부분의 WPF 태그 확장은 특성 구문이 불가능한 속성에 대한 특성 구문을 사용하도록 설정합니다. 예를 들어 <xref:System.Windows.Style> 개체는 중첩된 일련의 개체 및 속성을 포함하는 비교적 복잡한 형식입니다. WPF의 스타일은 일반적으로 <xref:System.Windows.ResourceDictionary>의 리소스로 정의된 다음 리소스를 요청하는 두 WPF 태그 확장 중 하나를 통해 참조됩니다. 태그 확장은 속성 값의 평가를 리소스 조회로 연기하고 다음 예제와 <xref:System.Windows.FrameworkElement.Style%2A> 같이 특성 <xref:System.Windows.Style>구문에서 type 을 사용하여 속성 값을 제공할 수 있습니다.  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 여기서는 `StaticResource` 태그 <xref:System.Windows.StaticResourceExtension> 확장 구현을 제공하는 클래스를 식별합니다. 다음 문자열은 `MyStyle` 기본이 <xref:System.Windows.StaticResourceExtension> 아닌 생성자의 입력으로 사용되며, 여기서 확장 문자열에서 가져온 <xref:System.Windows.ResourceKey>매개 변수는 요청된 을 선언합니다. `MyStyle`리소스로 <xref:System.Windows.Style> 정의된 [x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) 값이 될 것으로 예상됩니다. [StaticResource 마크업 확장](staticresource-markup-extension.md) 사용 요청 리소스 로드 <xref:System.Windows.Style> 시간에 정적 리소스 조회 논리를 통해 속성 값을 제공 하는 데 사용 됩니다.  
  
 태그 확장에 대한 자세한 내용은 [XAML 태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요. 일반 .NET XAML 구현에서 활성화된 태그 확장 및 기타 XAML 프로그래밍 기능에 대한 참조는 [XAML 네임스페이스(x:)를 참조하십시오. 언어 기능](../../../desktop-wpf/xaml-services/namespace-language-features.md). WPF 별 태그 확장은 [WPF XAML 확장을](wpf-xaml-extensions.md)참조하십시오.  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>연결된 속성  
 연결된 속성은 XAML에 도입된 프로그래밍 개념으로, 특정 형식에서 속성을 소유하고 정의할 수 있지만 모든 요소의 특성 또는 속성 요소로 설정할 수 있습니다. 연결된 속성이 의도된 기본 시나리오는 태그 구조의 자식 요소가 모든 요소에서 광범위하게 공유된 개체 모델을 필요로 하지 않고 부모 요소에 정보를 보고할 수 있도록 하는 것입니다. 반대로 연결된 속성은 상위 요소에서 자식 요소에 정보를 보고하는 데 사용할 수 있습니다. 연결된 속성의 목적과 연결된 속성을 직접 만드는 방법에 대한 자세한 내용은 [연결된 속성 개요를](attached-properties-overview.md)참조하십시오.  
  
 연결된 속성은 *typeName*을 지정한다는 점에서 속성 요소 구문과 표면적으로 유사한 구문을 사용합니다. *속성이름* 조합입니다. 다음과 같은 두 가지 중요한 차이점이 있습니다.  
  
- *name 을*사용할 수 있습니다. *속성* 구문을 통해 연결된 속성을 설정하는 경우에도 속성 이름 조합입니다. 연결된 속성은 속성 이름을 한정하는 유일한 경우입니다.  
  
- 연결된 속성에 속성 요소 구문을 사용할 수도 있습니다. 그러나 일반적인 속성 요소 구문의 경우 지정한 *typeName은* 속성 요소를 포함하는 개체 요소입니다. 연결된 속성을 참조하는 경우 *typeName은* 포함된 개체 요소가 아니라 연결된 속성을 정의하는 클래스입니다.  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>연결된 이벤트  
 연결된 이벤트는 특정 형식에 의해 이벤트를 정의할 수 있지만 처리기는 모든 개체 요소에 연결할 수 있는 XAML에 도입된 또 다른 프로그래밍 개념입니다. WOF 구현에서 연결된 이벤트를 정의하는 형식은 서비스를 정의하는 정적 형식이며 경우에 따라 연결된 이벤트는 서비스를 노출하는 형식의 라우트된 이벤트 별칭에 의해 노출되는 경우가 많습니다. 연결된 이벤트에 대한 처리기는 특성 구문을 통해 지정됩니다. 연결된 이벤트와 마찬가지로 특성 구문은 연결된 이벤트에 대해 확장되어 *typeName*. *eventName* 사용, *여기서 typeName* 은 `Add` `Remove` 연결된 이벤트 인프라에 대한 이벤트 처리기 접근자와 이벤트 처리기 접근자가 제공하는 클래스이며 *eventName은* 이벤트 이름입니다.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>XAML 루트 요소의 해부학  
 다음 표에서는 루트 요소의 특정 특성을 보여 주며 세분화된 일반적인 XAML 루트 요소를 보여 주며 다음과 같은 특성을 보여 주며 다음과 같은 특성을 보여 주며 다음과 같은 일반적인 XAML 루트 요소를 보여 줄 수 있습니다.  
  
|||  
|-|-|  
|`<Page`|루트 요소의 개체 요소 열기|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|기본값[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]( ) XAML 네임스페이스|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML 언어 XAML 네임스페이스|  
|`x:Class="ExampleNamespace.ExampleCode"`|부분 클래스에 대해 정의된 코드 숨김에 태그를 연결하는 부분 클래스 선언|  
|`>`|루트에 대한 개체 요소의 끝입니다. 요소에 자식 요소가 포함되어 있기 때문에 개체가 아직 닫히지 않았습니다.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>선택 사항 및 권장되지 않는 XAML 사용  
 다음 섹션에서는 XAML 프로세서에서 기술적으로 지원되지만 XAML 원본이 포함된 응용 프로그램을 개발할 때 XAML 파일을 읽을 수 있는 XAML 파일을 방해하는 자세한 내용이나 기타 미적 문제를 생성하는 XAML 사용에 대해 설명합니다.  
  
### <a name="optional-property-element-usages"></a>선택적 속성 요소 사용  
 선택적 속성 요소 사용에는 XAML 프로세서가 암시적으로 간주하는 요소 콘텐츠 속성을 명시적으로 작성하는 것이 포함됩니다. 예를 들어 <xref:System.Windows.Controls.Menu>의 내용을 선언할 때 는 <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.Menu> `<Menu.Items>` 의 컬렉션을 속성 요소 태그로 명시적으로 선언하고, <xref:System.Windows.Controls.MenuItem> `<Menu.Items>`암시적 XAML 프로세서 동작을 사용하는 대신 에 <xref:System.Windows.Controls.Menu> 각각을 <xref:System.Windows.Controls.MenuItem> 배치할 수 <xref:System.Windows.Controls.ItemsControl.Items%2A> 있습니다. 경우에 따라 선택적 사용법은 태그에 표시된 개체 구조를 시각적으로 명확히 하는 데 도움이 될 수 있습니다. 또는 명시적 속성 요소 사용으로 인해 기술적으로 는 기능적이지만 특성 값 내에 중첩된 태그 확장과 같이 시각적으로 혼동되는 태그를 방지할 수 있습니다.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>전체 typeName.memberName 정규화된 특성  
 *형식 이름*입니다. *특성에* 대한 memberName 양식은 실제로 라우트된 이벤트 사례보다 더 보편적으로 작동합니다. 그러나 다른 상황에서는 양식이 불필요합니다. 다음 예제에서는 <xref:System.Windows.Controls.Control.Background%2A> 특성에 대한 세 가지 참조 각각이 완전히 동일합니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`해당 속성에 <xref:System.Windows.Controls.Button> 대한 정규화된 조회가<xref:System.Windows.Controls.Control.Background%2A> 성공하고(Control에서 상속) 개체 요소 또는 기본 클래스의 <xref:System.Windows.Controls.Button> 클래스이기 때문에 작동합니다. `Control.Background`클래스가 <xref:System.Windows.Controls.Control> 실제로 <xref:System.Windows.Controls.Control.Background%2A> 정의하고 <xref:System.Windows.Controls.Control> <xref:System.Windows.Controls.Button> 기본 클래스이기 때문에 작동합니다.  
  
 그러나 다음 *형식Name*. *memberName* 양식 예제가 작동하지 않으므로 주석이 표시됩니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>의 또 다른 <xref:System.Windows.Controls.Control>파생 클래스이며 <xref:System.Windows.Controls.Label> 개체 `Label.Background` 요소 내에서 지정한 경우 이 사용이 효과가 있었을 것입니다. 그러나 클래스 <xref:System.Windows.Controls.Label> 또는 기본 클래스가 <xref:System.Windows.Controls.Button>아니기 때문에 지정된 XAML 프로세서 `Label.Background` 동작은 연결된 속성으로 처리합니다. `Label.Background`사용 가능한 연결된 속성이 아니며 이 사용이 실패합니다.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName 속성 요소  
 어떻게 *typeName*. *memberName* 양식은 특성 구문, *baseTypeName*에 대해 작동합니다. *멤버이름* 구문은 속성 요소 구문에 대해 작동합니다. 예를 들어 다음 구문이 작동합니다.  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 여기서 속성 요소는 `Control.Background` `Button`속성 요소에 포함되어 있더라도 지정되었습니다.  
  
 그러나 *typeName*. *멤버이름* 양식 속성, *baseTypeName*. *memberName은* 태그에서 잘못된 스타일이며 이를 피해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [XAML 네임스페이스(x:) 언어 기능](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [WPF XAML 확장](wpf-xaml-extensions.md)
- [종속성 속성 개요](dependency-properties-overview.md)
- [TypeConverter 및 XAML](typeconverters-and-xaml.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](xaml-and-custom-classes-for-wpf.md)
