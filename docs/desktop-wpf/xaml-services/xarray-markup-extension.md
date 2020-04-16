---
title: x:Array 태그 확장
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433285"
---
# <a name="xarray-markup-extension"></a>x:Array 태그 확장

태그 확장을 통해 XAML의 개체 배열에 대한 일반적인 지원을 제공합니다. 이는 [MS-XAML]의 `x:ArrayExtension` XAML 형식에 해당합니다.

## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`typeName`|`x:Array` 포함할 형식의 이름입니다. `typeName`XAML 형식 정의를 포함하는 XAML 네임스페이스의 접두사일 수 있습니다.|
|`arrayContents`|내재 속성에 `ArrayExtension.Items` 할당된 항목 콘텐츠입니다. 일반적으로 이러한 항목은 `x:Array` 개폐 태그에 포함된 하나 이상의 개체 요소로 지정됩니다. 여기에 지정된 개체는 에 지정된 XAML 형식에 `typeName`할당할 수 있어야 합니다.|

## <a name="remarks"></a>설명

`Type`는 모든 `x:Array` 개체 요소에 필요한 특성입니다. `Type` 매개 변수 값은 `x:Type` 태그 확장을 사용할 필요가 없습니다. 형식의 짧은 이름은 문자열로 지정할 수 있는 XAML 형식입니다.

.NET XAML 서비스 구현에서 입력 XAML 형식과 생성된 <xref:System.Type> 배열의 출력 CLR 간의 관계는 태그 확장에 대한 서비스 컨텍스트의 영향을 받습니다. 출력은 <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> XAML 스키마 컨텍스트및 컨텍스트가 제공하는 <xref:System.Xaml.XamlType> 서비스를 기반으로 필요한 정보를 찾은 <xref:System.Windows.Markup.IXamlTypeResolver> 후 입력 된 XAML 형식의 출력입니다.

처리하면 배열 내용이 내장 속성에 `ArrayExtension.Items` 할당됩니다. <xref:System.Windows.Markup.ArrayExtension> 구현에서 이 정보는 <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>로 표시됩니다.

.NET XAML 서비스 구현에서 이 태그 확장에 대한 <xref:System.Windows.Markup.ArrayExtension> 처리는 클래스에 의해 정의됩니다. <xref:System.Windows.Markup.ArrayExtension>봉인되지 않으며 사용자 지정 배열 형식에 대한 태그 확장 구현의 기초로 사용될 수 있습니다.

`x:Array`XAML의 일반 언어 확장성을 위한 것입니다. 그러나 `x:Array` XAML 지원 컬렉션을 구조화된 속성 콘텐츠로 지정하는 특정 속성의 XAML 값을 지정하는 데도 유용할 수 있습니다. 예를 들어 사용이 있는 <xref:System.Collections.IEnumerable> 속성의 내용을 `x:Array` 지정할 수 있습니다.

`x:Array`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. `x:Array`대체 특성 값 처리를 `x:Array` 제공하는 대신 내부 텍스트 내용을 대체 처리하기 때문에 해당 규칙의 일부 예외입니다. 이 동작을 사용하면 기존 콘텐츠 모델에서 지원되지 않는 형식을 어레이로 그룹화하고 나중에 명명된 배열에 액세스하여 코드 숨미기에서 참조할 수 있습니다. 메서드를 <xref:System.Array> 호출하여 개별 배열 항목을 얻을 수 있습니다.

XAML의 모든 태그 확장은 중괄호(특성{,} `)` 구문에서) 중괄호를 사용하며, 이는 XAML 프로세서가 태그 확장이 특성 값을 처리해야 함을 인식하는 규칙입니다. 일반적으로 태그 확장에 대한 자세한 내용은 [XAML에 대한 변환기 및 마크업 확장자를](type-converters-and-markup-extensions.md)참조하십시오.

XAML 2009에서 `x:Array` 태그 확장 대신 언어 기본으로 정의됩니다. 자세한 내용은 [일반적인 XAML 언어 기본 값에 대한 기본 제공 형식을](types-for-primitives.md)참조하십시오.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

일반적으로 a를 `x:Array` 채우는 개체 요소는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML 네임스페이스에 있는 요소가 아니며 기본이 아닌 XAML 네임스페이스에 접두사 매핑이 필요합니다.

예를 들어 다음은 배열 수준에서 `sys` 접두사(및 또한)가 `x`정의된 두 문자열의 간단한 배열입니다.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

배열 요소로 사용되는 사용자 지정 형식의 경우 클래스는 XAML에서 개체 요소로 인스턴스화되기 위한 요구 사항도 지원해야 합니다. 자세한 내용은 [WPF에 대한 XAML 및 사용자 지정 클래스를](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)참조하십시오.

## <a name="see-also"></a>참조

- [태그 확장명 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
