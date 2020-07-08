---
title: QuotedPairReader 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051313"
---
# <a name="quotedpairreader-class"></a>QuotedPairReader 클래스

따옴표 붙은 문자열에서 따옴표로 묶인 (이스케이프 됨) 문자를 결정 합니다. 이 클래스는 상속할 수 없습니다.

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="countquotedchars-method"></a>CountQuotedChars 메서드

지정 된 문자열에서 따옴표 붙은 여러 개의 백슬래시를 포함 하 여 연속 된 따옴표 문자의 수를 계산 합니다. 예를 들어 문자열 `a\\\b` 및의 인덱스가 제공 된 경우 `4` `4` `b` 는가 따옴표 붙은이 고 따라서 앞에 오는 백슬래시 세 개 이므로 메서드는를 반환 합니다.

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a>매개 변수

- `data` <xref:System.String>

  연속 되는 따옴표 붙은 문자를 계산할 데이터 문자열입니다.

- `index` <xref:System.Int32>

  지정 된 문자열에서 최대 연속 따옴표 문자를 포함 하는 위치입니다.

- `permitUnicodeEscaping` <xref:System.Boolean>

  `true`유니코드 문자를 이스케이프 하도록 허용 하려면 그렇지 않으면 `false` 입니다.

### <a name="return-value"></a>반환 값

<xref:System.Int32?displayProperty=nameWithType>

`0`지정 된 인덱스에 있는 문자가 이스케이프 되지 않으면이 고, 그렇지 않으면입니다. 그렇지 않으면에서 문자를 포함 하 여 최대 연속 따옴표 안에 포함 된 문자 수입니다 `index` .

### <a name="exceptions"></a>예외

<xref:System.FormatException?displayProperty=nameWithType>

이스케이프 된 유니코드 문자를 찾았지만 허용 되지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
