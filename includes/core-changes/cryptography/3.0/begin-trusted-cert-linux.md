---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721316"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="3c832-101">Linux에서 루트 인증서에 대해 더 이상 지원되지 않는 "BEGIN TRUSTED CERTIFICATE" 구문</span><span class="sxs-lookup"><span data-stu-id="3c832-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="3c832-102">Linux 및 기타 Unix 유사 시스템(macOS 제외)의 루트 인증서는 표준 `BEGIN CERTIFICATE` PEM 헤더와 OpenSSL별 `BEGIN TRUSTED CERTIFICATE` PEM 헤더의 두 가지 형태로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="3c832-103">후자 구문은 .NET Core의 <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> 클래스와의 호환성 문제가 발생한 추가 구성을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="3c832-104">.NET Core 3.0부터 체인 엔진이 `BEGIN TRUSTED CERTIFICATE` 루트 인증서 콘텐츠를 더 이상 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3c832-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3c832-105">Change description</span></span>

<span data-ttu-id="3c832-106">이전에는 `BEGIN CERTIFICATE` 및 `BEGIN TRUSTED CERTIFICATE` 구문이 모두 루트 신뢰 목록을 채우는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="3c832-107">`BEGIN TRUSTED CERTIFICATE` 구문이 사용되고 파일에 추가 옵션이 지정된 경우 <xref:System.Security.Cryptography.X509Certificates.X509Chain>에서 체인 트러스트가 명시적으로 허용되지 않았음을 보고했을 수 있습니다(<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="3c832-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="3c832-108">그러나 인증서가 이전에 로드된 파일에서 `BEGIN CERTIFICATE` 구문으로 지정된 경우에는 체인 트러스트가 허용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="3c832-109">.NET Core 3.0부터 `BEGIN TRUSTED CERTIFICATE` 콘텐츠를 더 이상 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="3c832-110">표준 `BEGIN CERTIFICATE` 구문을 통해서도 인증서가 지정되지 않은 경우 <xref:System.Security.Cryptography.X509Certificates.X509Chain>은 루트를 신뢰할 수 없음으로 보고합니다(<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="3c832-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3c832-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3c832-111">Version introduced</span></span>

<span data-ttu-id="3c832-112">3.0</span><span class="sxs-lookup"><span data-stu-id="3c832-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3c832-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3c832-113">Recommended action</span></span>

<span data-ttu-id="3c832-114">대부분의 애플리케이션은 이러한 변경의 영향을 받지 않지만 권한 문제로 인해 루트 인증서 원본을 모두 볼 수 없는 애플리케이션은 업그레이드 후 예기치 않은 `UntrustedRoot` 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="3c832-115">많은 Linux 배포(또는 배포판)는 루트 인증서를 파일당 하나의 인증서 디렉터리 및 하나의 파일 연결의 두 위치에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="3c832-116">일부 배포판에서는 파일당 하나의 인증서 디렉터리가 `BEGIN TRUSTED CERTIFICATE` 구문을 사용하는 반면 파일 연결은 표준 `BEGIN CERTIFICATE` 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="3c832-117">사용자 지정 루트 인증서를 이러한 위치 중 하나 이상에 `BEGIN CERTIFICATE`로 추가하고 두 위치를 모두 애플리케이션에서 읽을 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="3c832-118">일반적인 디렉터리는 */etc/ssl/certs/* 이고 일반적인 연결 파일은 */etc/ssl/cert.pem*입니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="3c832-119">`openssl version -d` 명령을 사용하여 */etc/ssl/* 과 다를 수 있는 플랫폼별 루트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="3c832-120">예를 들어 Ubuntu 18.04에서 디렉터리는 */usr/lib/ssl/certs/* 이고 파일은 */usr/lib/ssl/cert.pem*입니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="3c832-121">그러나 */usr/lib/ssl/certs/* 는 */etc/ssl/certs/* 에 대한 symlink이며 */usr/lib/ssl/cert.pem*은 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c832-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

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

#### <a name="category"></a><span data-ttu-id="3c832-122">범주</span><span class="sxs-lookup"><span data-stu-id="3c832-122">Category</span></span>

<span data-ttu-id="3c832-123">암호화</span><span class="sxs-lookup"><span data-stu-id="3c832-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3c832-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3c832-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
