---
title: MailBnfHelper 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990468"
---
# <a name="mailbnfhelper-class"></a>MailBnfHelper 클래스

인터넷 메시지 형식 문자열을 구문 분석 하는 유틸리티 메서드를 포함 합니다. 이 클래스는 상속할 수 없습니다.

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="ascii7bitmaxvalue-field"></a>Ascii7bitMaxValue 필드

최대 7 비트 Ascii 값을 나타냅니다.

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a>텍스트 필드

Atom에 허용 되는 문자를 나타냅니다.

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a>CR 필드

캐리지 리턴 문자를 나타냅니다.

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a>Ctext 필드

주석 내에서 허용 되는 문자를 나타냅니다.

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a>점 필드

전체 중지 문자 ()를 나타냅니다 `.` .

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a>EndComment 필드

주석의 끝을 지정 하는 문자를 나타냅니다.

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a>LF 필드

줄 바꿈 문자를 나타냅니다.

```csharp
internal static readonly char LF
```

## <a name="space-field"></a>공간 필드

공백 문자를 나타냅니다.

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a>StartComment 필드

주석의 시작을 지정 하는 문자를 나타냅니다.

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a>탭 필드

탭 문자를 나타냅니다.

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
