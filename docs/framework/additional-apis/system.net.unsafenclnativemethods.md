---
description: '자세히 알아보기: UnsafeNclNativeMethods 클래스'
title: UnsafeNclNativeMethods 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa1084efddae0ba5cbfc9a949dcd94d2c64f3272
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699495"
---
# <a name="unsafenclnativemethods-class"></a>UnsafeNclNativeMethods 클래스

안전 하지 않은 네이티브 네트워킹 메서드를 가져오는 클래스를 포함 합니다. 이 클래스는 상속될 수 없습니다.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="nativepki-class"></a>NativePKI 클래스

crypt32.dll에서 가져온 메서드를 포함 합니다. 이러한 메서드는 HTTPS (하이퍼텍스트 전송 프로토콜 보안)를 사용 하는 경우 인증서를 처리 합니다. 이 클래스는 상속될 수 없습니다.

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a>NativePKI. FindClientCertificates 메서드

서버에 보낼 사용 가능한 클라이언트 인증서를 검색 합니다.

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a>반환 값

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

사용 가능한 클라이언트 인증서의 컬렉션입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
