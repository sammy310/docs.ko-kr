---
title: x:Uid 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 3de02702e6fd2be63bc2d099dad11f896b281ad1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543500"
---
# <a name="xuid-directive"></a>x:Uid 지시문

태그 요소에 대 한 고유 식별자를 제공 합니다. 대부분의 시나리오에서이 고유 식별자는 XAML 지역화 프로세스 및 도구에서 사용 됩니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`identifier`|소비자가 해석할 때 파일에서 고유 해야 하는 수동으로 만들거나 자동 생성 된 문자열입니다 `x:Uid` .|

## <a name="remarks"></a>설명

[MS XAML]에서 `x:Uid` 는 지시문으로 정의 됩니다. 자세한 내용은 [ \[ \] 5.3.6 섹션](/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조 하세요.

`x:Uid` 는 `x:Name` 언급 된 XAML 지역화 시나리오로 인해와의 불연속 이며 지역화에 사용 되는 식별자에는의 프로그래밍 모델 의미에 대 한 종속성이 없습니다 `x:Name` . 또한 `x:Name` 는 xaml 이름 범위를 제어 하지만는 `x:Uid` 고유성 적용의 xaml 언어 정의 개념의 영향을 받지 않습니다. XAML 프로세서 (지역화 프로세스의 일부가 아닌 프로세서)는 값의 고유성을 적용할 수 없습니다 `x:Uid` . 이러한 책임은 개념적으로 값을 보낸 사람에 게 있습니다. `x:Uid`단일 XAML 소스 내에서 값의 고유성이 예상한 것은 전용 세계화 프로세스 또는 도구와 같은 값의 소비자에 게 적합 합니다. 일반적인 고유성 모델은 값이 `x:Uid` XAML을 나타내는 XML로 인코딩된 파일 내에서 고유 하다는 것입니다.

특정 XAML 스키마에 대 한 중요 한 지식이 있는 도구는 `x:Uid` 태그에서 텍스트 문자열 값이 발견 되는 경우를 포함 하 여 true로 지역화 가능한 문자열만 적용 하도록 선택할 수 있습니다.

프레임 워크는 `x:Uid` 정의 형식에 특성을 적용 하 여 개체 모델의 특정 속성을 별칭으로 지정할 수 있습니다 <xref:System.Windows.Markup.UidPropertyAttribute> . 프레임 워크에서 특정 속성을 지정 하는 경우 `x:Uid` 동일한 개체에서 및 별칭이 지정 된 멤버를 모두 지정할 수는 없습니다. `x:Uid`및 별칭이 지정 된 멤버를 모두 지정 하는 경우 일반적으로 .NET XAML 서비스 API가 <xref:System.Xaml.XamlDuplicateMemberException> 이 경우를 throw 합니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

WPF 지역화 프로세스 및 BAML 형식의 XAML에서의 역할에 대 한 자세한 내용은 `x:Uid` [Wpf 용 전역화](/dotnet/desktop/wpf/advanced/globalization-for-wpf) 를 참조 하세요. <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>참조

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [WPF의 전역화](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
