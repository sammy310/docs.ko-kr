---
title: '호환성이 손상되는 변경: Linux의 .NET용 기본 TLS 암호 그룹'
description: Linux에서 .NET이 TLS/SSL을 수행할 때 기본 암호 그룹에 대한 OpenSSL 구성을 따르는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/16/2020
ms.openlocfilehash: f1c23517161ac213a9cd7cf6e7da8eebeb91583b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759572"
---
# <a name="default-tls-cipher-suites-for-net-on-linux"></a>Linux의 .NET용 기본 TLS 암호 그룹

Linux에서 .NET은 이제 <xref:System.Net.Security.SslStream> 클래스를 통해 TLS/SSL을 수행하거나 <xref:System.Net.Http.HttpClient> 클래스를 통해 HTTPS와 같은 상위 수준 작업을 수행할 때 기본 암호 그룹에 대한 OpenSSL 구성을 따릅니다. 기본 암호 그룹이 명시적으로 구성되지 않은 경우 Linux의 .NET은 엄격하게 제한된 허용 암호 그룹 목록을 사용합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 .NET은 기본 암호 그룹에 대한 시스템 구성을 고려하지 않습니다. Linux의 .NET용 기본 암호 그룹 목록은 매우 관대합니다.

.NET 5.0부터 Linux의 .NET은 *openssl.cnf* 에 지정된 경우 기본 암호 그룹에 대한 OpenSSL 구성을 따릅니다. 암호 그룹이 명시적으로 구성되지 않은 경우 허용되는 유일한 암호 그룹은 다음과 같습니다.

- TLS 1.3 암호 그룹
- TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256

이 대체 기본값에는 TLS 1.0 또는 TLS 1.1과 호환되는 암호 그룹이 포함되어 있지 않으므로 이러한 이전 프로토콜 버전은 기본적으로 효과적으로 사용하지 않도록 설정됩니다.

특정 세션에 대해 SslStream에 CipherSuitePolicy 값을 제공하면 구성 파일 콘텐츠 및/또는 .NET 대체 기본값이 계속 대체됩니다.

## <a name="reason-for-change"></a>변경 이유

Linux에서 .NET을 실행하는 사용자가 <xref:System.Net.Security.SslStream>의 기본 구성을 타사 평가 도구에서 높은 보안 등급을 제공했던 구성으로 변경하도록 요청했습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

새로운 기본값은 최신 클라이언트 또는 서버와 통신할 때 사용할 수 있습니다. 기본 암호 그룹 목록을 확장하여 레거시 클라이언트를 허용하거나 레거시 서버에 연결하는 경우 `CipherSuitePolicy` 값을 지정하거나 OpenSSL 구성 파일을 변경합니다. 대부분의 Linux 배포에서 OpenSSL 구성 파일은 */etc/ssl/openssl.cnf* 에 있습니다.

이 샘플 *opensssl.cnf* 파일은 Linux의 .NET 5.0 이상에 대한 기본 암호 그룹 정책과 동일한 최소 파일입니다. 시스템 파일을 바꾸는 대신 이러한 개념을 시스템에 있는 파일과 병합합니다.

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

Red Hat Enterprise Linux, CentOS 및 Fedora 배포에서 .NET 애플리케이션은 기본적으로 시스템 전체 암호화 정책에서 허용되는 암호 그룹을 사용합니다. 이러한 배포에서는 *openssl.cnf* 대신 암호화 정책 구성을 사용합니다.

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
