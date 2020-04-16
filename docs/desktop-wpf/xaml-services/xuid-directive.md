---
title: x:Uid 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432619"
---
# <a name="xuid-directive"></a>x:Uid 지시문

태그 요소에 대한 고유 식별자를 제공합니다. 대부분의 시나리오에서 이 고유 식별자는 XAML 지역화 프로세스 및 도구에서 사용됩니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`identifier`|`x:Uid` 소비자가 해석할 때 파일에서 고유해야 하는 수동으로 만들거나 자동으로 생성된 문자열입니다.|

## <a name="remarks"></a>설명

[MS-XAML]에서 `x:Uid` 지시문으로 정의됩니다. 자세한 내용은 [ \[MS-XAML\] 섹션 5.3.6을](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))참조하십시오.

`x:Uid`명시된 XAML `x:Name` 지역화 시나리오와 지역화에 사용되는 식별자가 `x:Name`의 프로그래밍 모델 의미에 종속되지 않도록 둘 다에서 분리됩니다. 또한 `x:Name` XAML 네임스코프의 적용을 받습니다. `x:Uid` 그러나 XAML 언어 정의 된 고유성 적용 개념에 의해 제어 되지 않습니다. 넓은 의미에서 XAML 프로세서(지역화 프로세스의 일부가 아닌 프로세서)는 값의 `x:Uid` 고유성을 적용할 것으로 예상되지 않습니다. 그 책임은 개념적으로 값의 창시자에 있습니다. 단일 XAML `x:Uid` 소스 내에서 값의 고유성에 대한 기대는 전용 전역화 프로세스 또는 도구와 같은 값의 소비자에게 적합합니다. 일반적인 고유성 모델은 `x:Uid` XAML을 나타내는 XML 인코딩된 파일 내에서 값이 고유하다는 것입니다.

특정 XAML 스키마에 대한 상당한 지식이 있는 `x:Uid` 도구는 태그에서 텍스트 문자열 값이 발생하는 모든 경우에 적용되는 대신 실제 지역화 가능한 문자열에만 적용하도록 선택할 수 있습니다.

프레임워크는 정의 형식에 특성을 `x:Uid` <xref:System.Windows.Markup.UidPropertyAttribute> 적용하여 개체 모델의 특정 속성을 별칭으로 지정할 수 있습니다. 프레임워크에서 특정 속성을 지정하는 경우 동일한 개체에 `x:Uid` 둘 다와 별칭 멤버를 지정하는 것은 유효하지 않습니다. 둘 `x:Uid` 다 와 별칭 멤버를 지정 하는 경우 .NET <xref:System.Xaml.XamlDuplicateMemberException> XAML 서비스 API는 일반적으로이 경우에 대 한 throw합니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

WPF 지역화 프로세스 `x:Uid` 및 BaML 형태의 XAML에서의 역할에 대한 자세한 내용은 [WPF](../../framework/wpf/advanced/globalization-for-wpf.md) 또는<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>참조

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [WPF의 전역화](../../framework/wpf/advanced/globalization-for-wpf.md)
