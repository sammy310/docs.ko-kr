---
ms.openlocfilehash: 1d9a5bbea49730ee6cf99eaae6b20a0035e70b97
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135604"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a>Linux에서 루트 인증서에 대해 더 이상 지원되지 않는 "BEGIN TRUSTED CERTIFICATE" 구문

Linux 및 기타 Unix 유사 시스템(macOS 제외)의 루트 인증서는 표준 `BEGIN CERTIFICATE` PEM 헤더와 OpenSSL별 `BEGIN TRUSTED CERTIFICATE` PEM 헤더의 두 가지 형태로 제공될 수 있습니다. 후자 구문은 .NET Core의 <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> 클래스와의 호환성 문제가 발생한 추가 구성을 허용합니다. .NET Core 3.0부터 체인 엔진이 `BEGIN TRUSTED CERTIFICATE` 루트 인증서 콘텐츠를 더 이상 로드하지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 `BEGIN CERTIFICATE` 및 `BEGIN TRUSTED CERTIFICATE` 구문이 모두 루트 신뢰 목록을 채우는 데 사용되었습니다. `BEGIN TRUSTED CERTIFICATE` 구문이 사용되고 파일에 추가 옵션이 지정된 경우 <xref:System.Security.Cryptography.X509Certificates.X509Chain>에서 체인 트러스트가 명시적으로 허용되지 않았음을 보고했을 수 있습니다(<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>). 그러나 인증서가 이전에 로드된 파일에서 `BEGIN CERTIFICATE` 구문으로 지정된 경우에는 체인 트러스트가 허용되었습니다.

.NET Core 3.0부터 `BEGIN TRUSTED CERTIFICATE` 콘텐츠를 더 이상 읽지 않습니다. 표준 `BEGIN CERTIFICATE` 구문을 통해서도 인증서가 지정되지 않은 경우 <xref:System.Security.Cryptography.X509Certificates.X509Chain>은 루트를 신뢰할 수 없음으로 보고합니다(<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

대부분의 애플리케이션은 이러한 변경의 영향을 받지 않지만 권한 문제로 인해 루트 인증서 원본을 모두 볼 수 없는 애플리케이션은 업그레이드 후 예기치 않은 `UntrustedRoot` 오류가 발생할 수 있습니다.

많은 Linux 배포(또는 배포판)는 루트 인증서를 파일당 하나의 인증서 디렉터리 및 하나의 파일 연결의 두 위치에 씁니다. 일부 배포판에서는 파일당 하나의 인증서 디렉터리가 `BEGIN TRUSTED CERTIFICATE` 구문을 사용하는 반면 파일 연결은 표준 `BEGIN CERTIFICATE` 구문을 사용합니다. 사용자 지정 루트 인증서를 이러한 위치 중 하나 이상에 `BEGIN CERTIFICATE`로 추가하고 두 위치를 모두 애플리케이션에서 읽을 수 있는지 확인합니다.

일반적인 디렉터리는 */etc/ssl/certs/* 이고 일반적인 연결 파일은 */etc/ssl/cert.pem*입니다. `openssl version -d` 명령을 사용하여 */etc/ssl/* 과 다를 수 있는 플랫폼별 루트를 확인합니다. 예를 들어 Ubuntu 18.04에서 디렉터리는 */usr/lib/ssl/certs/* 이고 파일은 */usr/lib/ssl/cert.pem*입니다. 그러나 */usr/lib/ssl/certs/* 는 */etc/ssl/certs/* 에 대한 symlink이며 */usr/lib/ssl/cert.pem*은 존재하지 않습니다.

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

### <a name="category"></a>범주

암호화

### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
