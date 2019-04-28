---
title: DateTimeOffset 개체 인스턴스화
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11f62b8fe8a28d6fe6401d53dac4b9bc1c45b21d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669110"
---
# <a name="instantiating-a-datetimeoffset-object"></a>DateTimeOffset 개체 인스턴스화

<xref:System.DateTimeOffset> 구조체는 새 <xref:System.DateTimeOffset> 값을 만들 수 있는 여러 가지 방법을 제공합니다. 새 인스턴스화하기 위한 사용할 수 있는 방법에 직접 해당 하는 많은 <xref:System.DateTime> 값, 날짜 및 시간 값을 utc (협정 세계시) 오프셋을 지정할 수 있도록 향상 되었습니다. 특히 인스턴스화할 수 있습니다는 <xref:System.DateTimeOffset> 다음과 같은 방법으로 값:

* 날짜 및 시간 리터럴을 사용 하 여

* 호출 하 여를 <xref:System.DateTimeOffset> 생성자입니다.

* 값을 암시적으로 변환 하 여 <xref:System.DateTimeOffset> 값입니다.

* 날짜 및 시간의 문자열 표현 구문 분석

이 항목에서는 새 인스턴스화의 이러한 메서드를 설명 하는 큰 세부 정보 및 코드 예제를 제공 <xref:System.DateTimeOffset> 값입니다.

## <a name="date-and-time-literals"></a>날짜 및 시간 리터럴

지 원하는 언어를 인스턴스화하는 가장 일반적인 방법 중 하나에 대 한는 <xref:System.DateTime> 값이 날짜 및 시간을 하드 코딩 된 리터럴 값으로 제공 합니다. 예를 들어, 다음 Visual Basic 코드 만듭니다는 <xref:System.DateTime> 값인 2008 년 1 월 1 일 오전 10 시에 개체입니다.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<xref:System.DateTimeOffset> 지 원하는 언어를 사용 하는 경우 날짜 및 시간 리터럴을 사용 하 여 값 초기화할 수도 있습니다 <xref:System.DateTime> 리터럴. 예를 들어, 다음 Visual Basic 코드 만듭니다는 <xref:System.DateTimeOffset> 개체입니다.

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

콘솔 출력에서 볼 수 있듯이 <xref:System.DateTimeOffset> 값이이 방법으로 만든 현지 표준 시간대의 오프셋으로 할당 됩니다. 즉, 한 <xref:System.DateTimeOffset> 리터럴 문자를 사용 하 여 할당 된 값 다른 컴퓨터에서 코드를 실행 하는 경우 단일 시점을 식별 하지 않습니다.

## <a name="datetimeoffset-constructors"></a>DateTimeOffset 생성자

<xref:System.DateTimeOffset> 형식 6 개 생성자를 정의 합니다. 에 직접적으로 해당 중 4 개 <xref:System.DateTime> 형식의 추가 매개 변수를 사용 하 여 생성자 <xref:System.TimeSpan> 날짜를 정의 하 고 UTC에서의 시간 오프셋입니다. 정의할 수 있습니다는 <xref:System.DateTimeOffset> 개별 날짜 및 시간 구성 요소 값을 기준으로 하는 값입니다. 예를 들어, 다음 코드를 사용 하 여 이러한 네 가지 생성자 인스턴스화할 <xref:System.DateTimeOffset> 2008 년 7 월 1의 동일한 값을 사용 하 여 개체 오전 12 시 05 01:00입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

경우 값을 <xref:System.DateTimeOffset> 사용 하 여 인스턴스화된 개체를 <xref:System.Globalization.PersianCalendar> 개체 생성자에 인수 중 하나로 콘솔에 표시 되 면 페르시아 력의 아니라 그레고리오 력 날짜로 표시 됩니다. 페르시아력을 사용 하 여 날짜를 출력 하려면에서 예제를 참조 하세요.를 <xref:System.Globalization.PersianCalendar> 항목입니다.

다른 두 명의 생성자를 만듭니다는 <xref:System.DateTimeOffset> 에서 개체를 <xref:System.DateTime> 값입니다. 그 중 첫 번째 단일 매개 변수가 합니다 <xref:System.DateTime> 변환할 값을 <xref:System.DateTimeOffset> 값입니다. 결과의 오프셋 <xref:System.DateTimeOffset> 값에 따라 달라 집니다는 <xref:System.DateTime.Kind%2A> 생성자의 단일 매개 변수 속성. 값이 같으면 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>에 오프셋으로 설정 되었습니다 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다. 그렇지 않은 경우 해당 오프셋은 현지 표준 시간대의 값으로 설정됩니다. 다음 예제에서는 인스턴스화하는이 생성자의 사용을 보여 줍니다. <xref:System.DateTimeOffset> UTC 및 현지 표준 시간대를 나타내는 개체:

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> 오버 로드를 호출 합니다 <xref:System.DateTimeOffset> 생성자는 단일 <xref:System.DateTime> 매개 변수는 암시적으로 변환 수행을 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값.

만든 두 번째 생성자는를 <xref:System.DateTimeOffset> 에서 개체를 <xref:System.DateTime> 값에 두 개의 매개 변수:는 <xref:System.DateTime> 변환할 값 및 <xref:System.TimeSpan> UTC에서 오프셋의 날짜 및 시간을 나타내는 값입니다. 이 오프셋된 값과 일치 해야 합니다 <xref:System.DateTime.Kind%2A> 생성자의 첫 번째 매개 변수의 속성 또는 <xref:System.ArgumentException> throw 됩니다. 경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수의 속성은 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, 두 번째 매개 변수의 값 이어야 합니다 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다. 경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수의 속성은 <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, 두 번째 매개 변수의 값에 로컬 시스템의 표준 시간대의 오프셋 이어야 합니다. 경우는 <xref:System.DateTime.Kind%2A> 첫 번째 매개 변수의 속성은 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 오프셋을 유효한 값이 될 수 있습니다. 다음 코드를 변환 하려면이 생성자 호출을 보여 줍니다 <xref:System.DateTime> 에 <xref:System.DateTimeOffset> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a>암시적 형식 변환

<xref:System.DateTimeOffset> 형식이 암시적 형식 변환을 지원:에서 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값입니다. 암시적 형식 변환은 명시적 캐스팅(C#의 경우) 또는 변환(Visual Basic의 경우)을 필요로 하지 않고 정보를 손실하지 않는 형식 간의 변환입니다. 이를 사용하면 다음과 같은 코드를 사용할 수 있습니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

결과의 오프셋 <xref:System.DateTimeOffset> 값에 따라 달라 집니다는 <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> 속성 값입니다. 값이 같으면 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>에 오프셋으로 설정 되었습니다 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>합니다. 해당 값이 하나 <xref:System.DateTimeKind.Local?displayProperty=nameWithType> 또는 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, 오프셋은 현지 표준 시간대를 설정 합니다.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>날짜 및 시간의 문자열 표현 구문 분석

합니다 <xref:System.DateTimeOffset> 형식 날짜의 문자열 표현을 변환 및 시간을 할 수 있는 4 개의 메서드를 지 원하는 <xref:System.DateTimeOffset> 값:

* <xref:System.DateTimeOffset.Parse%2A>시간 및 날짜의 문자열 표현으로 변환 하려고 시도 하는 <xref:System.DateTimeOffset> 값 및 변환에 실패 하면 예외를 throw 합니다.

* <xref:System.DateTimeOffset.TryParse%2A>시간 및 날짜의 문자열 표현으로 변환 하려고 시도 하는 <xref:System.DateTimeOffset> 값과 반환 `false` 변환에 실패 하는 경우.

* <xref:System.DateTimeOffset.ParseExact%2A>에 지정 된 형식으로의 시간과 날짜의 문자열 표현으로 변환 하려고는 <xref:System.DateTimeOffset> 값입니다. 변환이 실패하면 메서드는 예외를 throw합니다.

* <xref:System.DateTimeOffset.TryParseExact%2A>에 지정 된 형식으로의 시간과 날짜의 문자열 표현으로 변환 하려고는 <xref:System.DateTimeOffset> 값입니다. 변환에 실패하는 경우 메서드가 `false`을 반환합니다.

다음 예제를 인스턴스화할의 이러한 4 개의 문자열 변환 메서드 각각에 대 한 호출을 <xref:System.DateTimeOffset> 값입니다.

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
