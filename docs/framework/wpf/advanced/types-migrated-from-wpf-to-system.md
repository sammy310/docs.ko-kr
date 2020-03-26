---
title: WPF에서 System.Xaml로 마이그레이션된 형식
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249815"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>WPF에서 System.Xaml로 마이그레이션된 형식

.NET Framework 3.5 및 .NET Framework 3.0에서는 WPF(Windows 프레젠테이션 파운데이션)와 Windows 워크플로 우대 재단에 XAML 언어 구현이 모두 포함되었습니다. WPF XAML 구현에 대해 확장성을 제공한 공용 형식은 대부분 WindowsBase, PresentationCore 및 PresentationFramework 어셈블리에 있었습니다. 마찬가지로 Windows 워크플로 파운데이션 XAML에 대한 확장성을 제공하는 공용 형식은 System.Workflow.ComponentModel 어셈블리에 존재했습니다. .NET 프레임워크 4에서 일부 XAML 관련 형식이 System.Xaml 어셈블리로 마이그레이션되었습니다. XAML 언어 서비스의 일반적인 .NET Framework 구현을 사용하면 원래 특정 프레임워크의 XAML 구현에 의해 정의되었지만 이제는 전체 .NET Framework 4 XAML 언어 지원의 일부인 많은 XAML 확장성 시나리오를 사용할 수 있습니다. 이 문서에서는 마이그레이션된 형식을 나열하고 마이그레이션과 관련된 문제에 대해 설명합니다.

## <a name="assemblies-and-namespaces"></a>어셈블리 및 네임스페이스

.NET Framework 3.5 및 .NET Framework 3.0에서 XAML을 지원하기 위해 <xref:System.Windows.Markup> WPF가 구현한 형식은 일반적으로 네임스페이스에 있었습니다. 이러한 형식은 대부분 WindowsBase 어셈블리에 있었습니다.

.NET 프레임워크 4에는 새 <xref:System.Xaml> 네임스페이스와 새 System.Xaml 어셈블리가 있습니다. 원래 WPF XAML에 대해 구현된 많은 형식이 이제 XAML 구현에 대한 확장성 지점 또는 서비스로 제공됩니다. 보다 일반적인 시나리오에 사용할 수 있도록 하는 작업의 일부로 원래의 WPF 어셈블리에서 System.Xaml 어셈블리로 형식이 전달됩니다. 이렇게 하면 다른 프레임워크(예: WPF 및 Windows 워크플로 재단)의 어셈블리를 포함하지 않고도 XAML 확장성 시나리오를 사용할 수 있습니다.

마이그레이션된 형식의 경우 대부분의 형식이 <xref:System.Windows.Markup> 네임스페이스에 계속 유지됩니다. 이는 부분적으로 기존 구현의 CLR 네임스페이스 매핑이 파일별로 분할되지 않도록 하기 위한 것이었습니다. 따라서 .NET <xref:System.Windows.Markup> Framework 4의 네임스페이스에는 일반 XAML 언어 지원 형식(System.Xaml 어셈블리)과 WPF XAML 구현(WindowsBase 및 기타 WPF 어셈블리)과 관련된 형식이 혼합되어 있습니다. System.Xaml로 마이그레이션되었지만 이전에 WPF 어셈블리에 있었던 형식은 WPF 어셈블리의 버전 4에서 형식 전달을 지원합니다.

### <a name="workflow-xaml-support-types"></a>워크플로 XAML 지원 형식

또한 Windows 워크플로 우로 재단은 XAML 지원 유형을 제공했으며 대부분의 경우 이러한 이름은 WPF와 동일한 짧은 이름을 가지고 있었습니다. 다음은 Windows 워크플로 기반 XAML 지원 유형 목록입니다.

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

이러한 지원 유형은 .NET Framework 4용 Windows 워크플로 파운데이션 어셈블리에 여전히 존재하며 특정 Windows 워크플로 파운데이션 응용 프로그램에 계속 사용할 수 있습니다. 그러나 Windows 워크플로 파운데이션을 사용하지 않는 응용 프로그램이나 프레임워크에서 참조해서는 안 됩니다.

## <a name="markupextension"></a>MarkupExtension

.NET 프레임워크 3.5 및 .NET Framework 3.0에서 WPF에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스는 WindowsBase 어셈블리에 있었습니다. Windows 워크플로 파운데이션에 <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>대한 병렬 클래스는 System.Workflow.ComponentModel 어셈블리에 존재했습니다. .NET 프레임워크 4에서 <xref:System.Windows.Markup.MarkupExtension> 클래스는 System.Xaml 어셈블리로 마이그레이션됩니다. .NET Framework 4에서는 <xref:System.Windows.Markup.MarkupExtension> 특정 프레임워크를 기반으로 하는 XAML 서비스뿐만 아니라 .NET XAML 서비스를 사용하는 모든 XAML 확장성 시나리오를 위한 것입니다. 가능한 경우 특정 프레임워크 또는 프레임워크의 사용자 코드도 XAML 확장에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스에서 빌드되어야 합니다.

## <a name="markupextension-supporting-service-classes"></a>MarkupExtension 지원 서비스 클래스

WPF용 .NET Framework 3.5 및 .NET Framework 3.0은 XAML에서 형식/속성 사용을 지원하기 위해 <xref:System.Windows.Markup.MarkupExtension> 구현자와 <xref:System.ComponentModel.TypeConverter> 구현에 사용할 수 있는 여러 서비스를 제공했습니다. 이러한 서비스는 다음과 같습니다.

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> .NET Framework 3.5의 태그 확장과 관련된 또 <xref:System.Windows.Markup.IReceiveMarkupExtension> 다른 서비스는 인터페이스입니다. <xref:System.Windows.Markup.IReceiveMarkupExtension>마이그레이션되지 않았으며 .NET `[Obsolete]` Framework 4로 표시됩니다. 이전에 <xref:System.Windows.Markup.IReceiveMarkupExtension> 을 사용한 시나리오에서는 대신 <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> 특성 콜백을 사용해야 합니다. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> 도 `[Obsolete]`로 표시됩니다.

## <a name="xaml-language-features"></a>XAML 언어 기능

WPF용 여러 XAML 언어 기능과 구성 요소는 이전에 PresentationFramework 어셈블리에 있었습니다. 이러한 항목은 XAML 태그로 태그 확장 사용을 노출하는 <xref:System.Windows.Markup.MarkupExtension> 서브클래스로 구현되었습니다. .NET Framework 4에서는 WPF 어셈블리를 포함하지 않는 프로젝트가 이러한 XAML 언어 수준 기능을 사용할 수 있도록 System.Xaml 어셈블리에 이러한 기능이 있습니다. WPF는 .NET Framework 4 응용 프로그램에 대해 동일한 구현을 사용합니다. 이 항목에 나열된 다른 경우와 마찬가지로, 지원 형식은 이전 참조가 손상되지 않도록 계속 <xref:System.Windows.Markup> 네임스페이스에 있습니다.

다음 표에는 System.Xaml에서 정의되는 XAML 기능 지원 클래스 목록이 포함되어 있습니다.

|XAML 언어 기능|사용|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

System.Xaml에 특정 지원 클래스가 없을 수도 있지만 이제 XAML 언어의 언어 기능 처리를 위한 일반적인 논리가 System.Xaml과 구현된 XAML 판독기 및 XAML 작성기에 상주합니다. 예를 들어 `x:TypeArguments` 는 System.Xaml 구현의 XAML 판독기 및 XAML 작성기에서 처리되는 특성입니다. XAML 노드 스트림에 기록될 수 있고, 기본(CLR 기반) XAML 스키마 컨텍스트 처리가 있으며, XAML 형식 시스템 표현을 포함합니다. 따라서 모든 XAML 언어 수준 기능에 대한 참조 설명서는 [WPF(Windows 프레젠테이션 기반)에 대한 데스크톱 가이드의](../../../desktop-wpf/overview/index.md) [XAML 서비스에](../../../desktop-wpf/xaml-services/index.md) 대한 하위 항목입니다.

## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer 및 지원 클래스

<xref:System.Windows.Markup.ValueSerializer> 클래스는 특히 직렬화 시 출력에 여러 모드 또는 노드가 필요할 수 있는 XAML 직렬화 사례를 위해 문자열로의 형식 변환을 지원합니다. .NET 프레임워크 3.5 및 .NET 프레임워크 <xref:System.Windows.Markup.ValueSerializer> 3.0에서 WPF용은 WindowsBase 어셈블리에 있었습니다. .NET Framework 4에서 <xref:System.Windows.Markup.ValueSerializer> 클래스는 System.Xaml에 있으며 WPF에서 빌드하는 XAML 확장성 시나리오뿐만 아니라 모든 XAML 확장성 시나리오를 위한 것입니다. <xref:System.Windows.Markup.IValueSerializerContext> (지원 서비스) 및 <xref:System.Windows.Markup.DateTimeValueSerializer> (특정 서브클래스)도 System.Xaml로 마이그레이션됩니다.

## <a name="xaml-related-attributes"></a>XAML 관련 특성

WPF XAML은 XAML 동작에 대한 특징을 나타내기 위해 CLR 형식에 적용할 수 있는 여러 특성을 포함했습니다. 다음은 .NET Framework 3.5 및 .NET Framework 3.0의 WPF 어셈블리에 있는 특성 목록입니다. 이러한 특성은 .NET 프레임워크 4의 System.Xaml로 마이그레이션됩니다.

- <xref:System.Windows.Markup.AmbientAttribute>

- <xref:System.Windows.Markup.ContentPropertyAttribute>

- <xref:System.Windows.Markup.ContentWrapperAttribute>

- <xref:System.Windows.Markup.DependsOnAttribute>

- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

- <xref:System.Windows.Markup.NameScopePropertyAttribute>

- <xref:System.Windows.Markup.RootNamespaceAttribute>

- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

- <xref:System.Windows.Markup.ValueSerializerAttribute>

- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

- <xref:System.Windows.Markup.XmlLangPropertyAttribute>

- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

- <xref:System.Windows.Markup.XmlnsPrefixAttribute>

## <a name="miscellaneous-classes"></a>기타 클래스

인터페이스는 <xref:System.Windows.Markup.IComponentConnector> .NET Framework 3.5 및 .NET Framework 3.0의 WindowsBase에 존재하지만 .NET 프레임워크 4의 System.Xaml에 있습니다. <xref:System.Windows.Markup.IComponentConnector> 는 주로 도구 지원 및 XAML 태그 컴파일러에 사용됩니다.

인터페이스는 <xref:System.Windows.Markup.INameScope> .NET Framework 3.5 및 .NET Framework 3.0의 WindowsBase에 존재하지만 .NET 프레임워크 4의 System.Xaml에 있습니다. <xref:System.Windows.Markup.INameScope> 는 XAML 네임스페이스에 대한 기본 작업을 정의합니다.

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>WPF 및 System.Xaml에 있는 공유 이름의 XAML 관련 클래스

다음 클래스는 .NET 프레임워크 4의 WPF 어셈블리와 System.Xaml 어셈블리 모두에 존재합니다.

`XamlReader`

`XamlWriter`

`XamlParseException`

WPF 구현은 <xref:System.Windows.Markup> 네임스페이스 및 PresentationFramework 어셈블리에 있습니다. System.Xaml 구현은 <xref:System.Xaml> 네임스페이스에 있습니다. WPF 형식을 사용하거나 WPF 형식에서 파생하는 경우 일반적으로 System.Xaml 구현 대신 <xref:System.Windows.Markup.XamlReader> 및 <xref:System.Windows.Markup.XamlWriter> 의 WPF 구현을 사용해야 합니다. 자세한 내용은 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 및 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>의 설명을 참조하세요.

WPF 어셈블리 및 System.Xaml에 대한 참조를 둘 다 포함하고 `include` 및 <xref:System.Windows.Markup> 네임스페이스에 모두 <xref:System.Xaml> 문을 사용하는 경우 형식을 명확하게 확인하기 위해 이러한 API에 대한 호출을 정규화해야 할 수도 있습니다.
