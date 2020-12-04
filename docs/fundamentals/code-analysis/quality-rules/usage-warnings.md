---
title: 사용 규칙 (코드 분석)
description: 코드 분석 사용 규칙에 대해 알아봅니다.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.usagerules
helpviewer_keywords:
- rules, usage
- managed code analysis rules, usage rules
- usage rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: c8b14d2f92502d5a82e41a322e599745bdcf8b85
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "96593529"
---
# <a name="usage-rules"></a>사용 규칙

사용 규칙은 .NET의 적절 한 사용을 지원 합니다.

## <a name="in-this-section"></a>섹션 내용

|규칙|설명|
|----------|-----------------|
|[CA1801: 사용되지 않은 매개 변수를 검토하세요.](ca1801.md)|메서드 시그니처에 메서드 본문에서 사용되지 않는 매개 변수가 있습니다.|
|[CA1816: GC.SuppressFinalize를 올바르게 호출하세요.](ca1816.md)|Dispose의 구현인 메서드는를 호출 하지 않고, `GC.SuppressFinalize` 호출의 구현이 아닌 메서드를 호출 하거나, 메서드를 `Dispose` `GC.SuppressFinalize` 호출 `GC.SuppressFinalize` 하 고 Visual Basic의 이외의 항목을 전달 `this` `Me` 합니다.|
|[CA2200: 스택 정보를 유지하도록 다시 throw하십시오.](ca2200.md)|예외가 다시 throw되며 예외가 throw 문에 명시적으로 지정되어 있습니다. throw 문에 예외를 지정하여 예외가 다시 throw되면 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다.|
|[CA2201: 예약된 예외 형식을 발생시키지 마세요.](ca2201.md)|이렇게 하면 원래 오류를 검색 하 고 디버그 하기가 어렵습니다.|
|[CA2207: 값 형식 정적 필드 인라인을 초기화하십시오.](ca2207.md)|값 형식에서 명시적인 정적 생성자를 선언합니다. 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.|
|[CA2208: 인수 예외를 올바르게 인스턴스화하세요.](ca2208.md)|ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 기본(매개 변수가 없는) 생성자를 호출했거나, ArgumentException 또는 ArgumentException에서 파생된 예외 형식의 매개 변수가 있는 생성자에 잘못된 문자열 인수가 전달되었습니다.|
|[CA2211: 비상수 필드는 노출되면 안 됩니다.](ca2211.md)|상수 또는 읽기 전용 정적 필드는 스레드로부터 안전 하지 않습니다. 이러한 필드에 대 한 액세스는 신중 하 게 제어 해야 하며 클래스 개체에 대 한 액세스를 동기화 하기 위한 고급 프로그래밍 기술이 필요 합니다.|
|[CA2213: 삭제 가능한 필드는 삭제해야 합니다.](ca2213.md)|을 구현 하는 형식은 <xref:System.IDisposable?displayProperty=fullName> 도 구현 하는 형식의 필드를 선언 `IDisposable` 합니다. `Dispose`필드의 메서드는 선언 형식의 메서드에서 호출 되지 않습니다 `Dispose` .|
|[CA2214: 재정의 가능한 메서드를 생성자에서 호출하지 마십시오.](ca2214.md)|생성자가 가상 메서드를 호출 하는 경우 메서드를 호출 하는 인스턴스에 대 한 생성자가 실행 되지 않았을 수 있습니다.|
|[CA2215: Dispose 메서드는 기본 클래스 Dispose를 호출해야 합니다.](ca2215.md)|형식이 삭제 가능한 형식에서 상속 되는 경우 `Dispose` 자체 메서드에서 기본 형식의 메서드를 호출 해야 합니다 `Dispose` .|
|[CA2216: 삭제 가능한 형식은 종료자를 선언해야 합니다.](ca2216.md)|을 구현 하 <xref:System.IDisposable?displayProperty=fullName> 고 관리 되지 않는 리소스의 사용을 제안 하는 필드를 포함 하는 형식에서는에 설명 된 대로 종료자를 구현 하지 않습니다 `Object.Finalize` .|
|[CA2217: 열거형을 FlagsAttribute로 표시하지 마세요.](ca2217.md)|외부에서 볼 수 있는 열거형은로 표시 되 `FlagsAttribute` 고, 두의 거듭제곱이 아닌 하나 이상의 값 또는 열거형에 정의 된 다른 값의 조합이 있습니다.|
|[CA2218: Equals를 재정할 때 GetHashCode를 재정의하세요.](ca2218.md)|Public 형식은를 재정의 <xref:System.Object.Equals%2A?displayProperty=fullName> 하지만는 재정의 하지 않습니다 <xref:System.Object.GetHashCode%2A?displayProperty=fullName> .|
|[CA2219: exception 절에서 예외를 발생시키지 마세요.](ca2219.md)|finally 또는 fault 절에서 예외가 발생하는 경우 새 예외가 활성 예외를 숨깁니다. filter 절에서 예외가 발생하는 경우 런타임이 자동으로 예외를 catch합니다. 이렇게 하면 원래 오류를 검색 하 고 디버그 하기가 어렵습니다.|
|[CA2224: 같음 연산자를 오버로드할 때 Equals를 재정의하세요.](ca2224.md)|Public 형식은 같음 연산자를 구현 하지만는 재정의 하지 않습니다 <xref:System.Object.Equals%2A?displayProperty=fullName> .|
|[CA2225: 연산자 오버로드에는 명명된 대체 항목이 있습니다.](ca2225.md)|연산자 오버로드가 감지되었으며 예상되는 이름의 대체 메서드를 찾을 수 없습니다. 명명 된 대체 멤버는 연산자와 같은 기능에 대 한 액세스를 제공 하며 오버 로드 된 연산자를 지원 하지 않는 언어로 프로그래밍 하는 개발자를 위해 제공 됩니다.|
|[CA2226: 연산자에는 대칭 오버로드가 있어야 합니다.](ca2226.md)|형식은 같음 또는 같지 않음 연산자를 구현 하며, 반대 연산자를 구현 하지 않습니다.|
|[CA2227: 컬렉션 속성은 읽기 전용이어야 합니다.](ca2227.md)|쓰기 가능한 컬렉션 속성을 통해 사용자는 컬렉션을 다른 컬렉션으로 바꿀 수 있습니다. 읽기 전용 속성은 컬렉션을 바꾸지 못하도록 하지만 개별 멤버를 설정하는 것은 여전히 가능합니다.|
|[CA2229: serialization 생성자를 구현하십시오.](ca2229.md)|이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다. 봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.|
|[CA2231: ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.](ca2231.md)|값 형식이를 재정의 `Object.Equals` 하지만 같음 연산자를 구현 하지 않습니다.|
|[CA2234: 문자열 대신 System.Uri 개체를 전달하세요.](ca2234.md)|이름에 "uri", "URI", "urn", "URN", "url" 또는 "URL"이 포함된 문자열 매개 변수가 있는 메서드가 호출되었습니다.  메서드의 선언 형식에는 매개 변수가 있는 해당 메서드 오버 로드가 포함 <xref:System.Uri?displayProperty=fullName> 됩니다.|
|[CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.](ca2235.md)|serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.|
|[CA2237: SerializableAttribute로 ISerializable 형식 표시](ca2237.md)|공용 언어 런타임에서 serializable로 인식 되려면 형식에서 인터페이스 구현을 통해 사용자 지정 serialization 루틴을 사용 하는 경우에도 형식을 SerializableAttribute 특성으로 표시 해야 합니다 `ISerializable` .|
|[CA2241: 서식 지정 메서드에 올바른 인수를 제공하십시오.](ca2241.md)|에 전달 된 형식 인수에 <xref:System.String.Format%2A?displayProperty=nameWithType> 각 개체 인수에 해당 하는 형식 항목이 포함 되어 있지 않거나 그 반대의 경우도 마찬가지입니다.|
|[CA2242: NaN에 대해 정확하게 테스트하십시오.](ca2242.md)|이 식은 또는에 대해 값을 테스트 `Single.Nan` `Double.Nan` 합니다. `Single.IsNan(Single)`또는 `Double.IsNan(Double)` 를 사용 하 여 값을 테스트 합니다.|
|[CA2243: 특성 문자열 리터럴이 올바르게 구문 분석되어야 합니다.](ca2243.md)|특성의 문자열 리터럴 매개 변수는 URL, GUID 또는 버전에 대해 올바르게 구문 분석 되지 않습니다.|
|[CA2244: 인덱싱된 요소의 초기화는 복제하면 안 됩니다.](ca2244.md)|개체 이니셜라이저에 동일한 상수 인덱스를 사용 하는 두 개 이상의 인덱싱된 요소 이니셜라이저가 있습니다. 마지막 이니셜라이저가 아닌 모두 중복 됩니다.|
|[CA2245: 속성을 자체에 할당하지 마세요.](ca2245.md)|속성이 실수로 자신에 게 할당 되었습니다.|
|[CA2246: 동일한 문에 기호 및 해당 멤버를 할당하지 마세요.](ca2246.md)|동일한 문에서 기호와 해당 멤버, 즉 필드 또는 속성을 할당 하는 것은 권장 되지 않습니다. 멤버 액세스에서 할당 전 기호의 이전 값을 사용 하거나이 문의 할당에서 새 값을 사용 하기 위한 것은 분명 하지 않습니다.|
|[CA2247: TaskCompletionSource 생성자로 전달된 인수는 TaskContinuationOptions 열거형이 아닌 TaskCreationOptions 열거형이어야 합니다.](ca2246.md)|TaskTaskCreationOptions Source에는 기본 작업을 제어 하는 생성자와 작업에 저장 된 개체 상태를 사용 하는 생성자가 있습니다.  실수로 TaskCreationOptions 대신 System.threading.tasks.taskcontinuationoptions를 전달 하면 호출은 옵션을 state로 처리 합니다.|
|[CA2248: ' Enum. HasFlag '에 올바른 ' enum ' 인수를 제공 하십시오.](ca2248.md)|메서드 호출에 인수로 전달 된 열거형 형식이 호출 하는 `HasFlag` 열거형 형식과 다릅니다.|
|[CA2249: ‘String.IndexOf’ 대신 ‘String.Contains’ 사용 고려](ca2249.md)|결과를 `string.IndexOf` 사용 하 여 부분 문자열의 존재 여부를 확인 하는 호출을로 바꿀 수 있습니다 `string.Contains` .|
