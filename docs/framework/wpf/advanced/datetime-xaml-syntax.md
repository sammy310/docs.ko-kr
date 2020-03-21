---
title: DateTime XAML 구문
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186325"
---
# <a name="datetime-xaml-syntax"></a>DateTime XAML 구문
및 및 와 <xref:System.Windows.Controls.Calendar> <xref:System.Windows.Controls.DatePicker>같은 일부 컨트롤에는 <xref:System.DateTime> 형식을 사용하는 속성이 있습니다. 일반적으로 런타임에 코드 숨김으로 이러한 컨트롤에 대해 초기 날짜 또는 시간을 지정하지만 XAML로 초기 날짜 또는 시간을 지정할 수 있습니다. WPF XAML 파서는 기본 제공 <xref:System.DateTime> XAML 텍스트 구문을 사용하여 값 구문 분석문제를 처리합니다. 이 항목에서는 <xref:System.DateTime> XAML 텍스트 구문의 세부 사항을 설명합니다.  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>DateTime XAML 구문을 사용하는 경우  
 날짜를 항상 XAML로 설정할 필요가 없으며 이 방법이 바람직하지 않을 수도 있습니다. 예를 들어 속성을 <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 사용하여 런타임에 날짜를 초기화하거나 사용자 입력을 기반으로 코드 숨결에서 캘린더에 대한 모든 날짜 조정을 수행할 수 있습니다. 그러나 컨트롤 <xref:System.Windows.Controls.Calendar> 템플릿과 <xref:System.Windows.Controls.DatePicker> 컨트롤 템플릿에서 날짜를 하드 코딩하려는 시나리오가 있습니다. 이러한 <xref:System.DateTime> 시나리오에 XAML 구문을 사용해야 합니다.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime XAML 구문이 기본 동작임  
 <xref:System.DateTime>는 CLR의 기본 클래스 라이브러리에 정의된 클래스입니다. 기본 클래스 라이브러리가 CLR의 나머지 부분과 관련되므로 클래스에 <xref:System.ComponentModel.TypeConverterAttribute> 적용하고 XAML에서 문자열을 처리하고 런타임 개체 모델로 변환하는 <xref:System.DateTime> 형식 변환기를 사용할 수 없습니다. 변환 동작을 제공하는 `DateTimeConverter` 클래스가 없습니다. 이 항목에서 설명하는 변환 동작은 WPF XAML 파서의 기본 동작입니다.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>DateTime XAML 구문의 형식 문자열  
 형식 문자열을 가진 <xref:System.DateTime> 의 형식을 지정할 수 있습니다. 형식 문자열은 값을 생성하는 데 사용할 수 있는 텍스트 구문을 공식화합니다. <xref:System.DateTime>기존 WPF 컨트롤의 값은 일반적으로 시간 <xref:System.DateTime> 구성 요소의 날짜 구성 요소만 사용합니다.  
  
 XAML에서 <xref:System.DateTime> 를 지정할 때 모든 형식 문자열을 서로 교환하여 사용할 수 있습니다.  
  
 이 항목에 구체적으로 표시되지 않은 형식 및 형식 문자열을 사용할 수도 있습니다. 기술적으로 WPF XAML <xref:System.DateTime> 파서에 의해 지정되고 구문 분석된 모든 값에 대한 XAML은 내부 호출을 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 사용하므로 XAML 입력에 대해 허용되는 모든 문자열을 사용할 수 있습니다. 자세한 내용은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>을 참조하세요.  
  
> [!IMPORTANT]
> DateTime XAML 구문은 `en-us` 항상 <xref:System.Globalization.CultureInfo> 네이티브 변환에 대해 사용됩니다. XAML 특성 <xref:System.Windows.FrameworkElement.Language%2A> 수준 `xml:lang` 형식 변환은 해당 컨텍스트 없이 작동하기 때문에 XAML의 값이나 값의 영향을 받지 않습니다. 일과 월이 표시되는 순서와 같은 문화적 차이로 인해 여기에 표시된 형식 문자열을 보간하지 마세요. 여기에 표시된 형식 문자열은 다른 문화권 설정에 관계없이 XAML을 구문 분석할 때 사용되는 정확한 형식 문자열입니다.  
  
 다음 섹션에서는 일부 공통 <xref:System.DateTime> 형식 문자열에 대해 설명합니다.  
  
### <a name="short-date-pattern-d"></a>간단한 날짜 패턴("d")  
 다음은 XAML의 짧은 <xref:System.DateTime> 날짜 형식을 보여 주며,  
  
 `M/d/YYYY`  
  
 WPF 컨트롤에서 일반적으로 사용하는 데 필요한 모든 정보를 지정하는 가장 간단한 형식이며 실수에 의한 표준 시간대 오프셋 및 시간 구성 요소의 영향을 받지 않으므로 다른 형식에 비해 권장됩니다.  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다.  
  
 `3/1/2010`  
  
 자세한 내용은 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>을 참조하세요.  
  
### <a name="sortable-datetime-pattern-s"></a>정렬 가능한 DateTime 패턴("s")  
 다음은 XAML에서 <xref:System.DateTime> 정렬 가능한 패턴을 보여 주며 다음과 같은 것입니다.  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123 패턴("r")  
 RFC1123 패턴은 문화권이 고정되어 있다는 이유로 RFC1123 패턴도 사용하는 다른 날짜 생성기의 문자열 입력이 될 수 있기 때문에 유용합니다. 다음은 XAML의 RFC1123 <xref:System.DateTime> 패턴을 보여 주며,  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>기타 형식 및 패턴  
 앞에서 설명한 <xref:System.DateTime> 것처럼 XAML의 입력으로 허용되는 모든 문자열로 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>XAML을 지정할 수 있습니다. 여기에는 다른 공식화된 형식(예: <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>특정 <xref:System.Globalization.DateTimeFormatInfo> 형식으로 공식화되지 않은 형식)이 포함됩니다. 예를 들어 양식은 `YYYY/mm/dd` 에 대한 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>입력으로 허용됩니다. 이 항목에서는 작동 가능한 모든 형식에 대해 설명하려고 하지 않으며 대신 간단한 날짜 패턴을 표준 사례로 권장합니다.  
  
## <a name="see-also"></a>참고 항목

- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
