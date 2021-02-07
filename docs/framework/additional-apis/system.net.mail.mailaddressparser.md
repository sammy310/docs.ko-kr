---
description: '자세히 알아보기: MailAddressParser 클래스'
title: MailAddressParser 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 5ad534e731e283f5449b3b8cc8e87628716da9b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699768"
---
# <a name="mailaddressparser-class"></a>MailAddressParser 클래스

RFC 2822에 설명 된 대로 전자 메일 주소를 구문 분석 합니다. 이 클래스는 상속될 수 없습니다.

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="parseaddress-method"></a>ParseAddress 메서드

지정 된 문자열에서 단일 전자 메일 주소를 구문 분석 합니다.

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a>매개 변수

`data` <xref:System.String>

구문 분석할 전자 메일 주소를 포함 하는 문자열입니다.

### <a name="return-value"></a>반환 값

<xref:System.Net.Mail.MailAddress>

유효한 전자 메일 주소입니다.

### <a name="exceptions"></a>예외

<xref:System.FormatException?displayProperty=nameWithType>

전자 메일 주소가 잘못 되었습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
