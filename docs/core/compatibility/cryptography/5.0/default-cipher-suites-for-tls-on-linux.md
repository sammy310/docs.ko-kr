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
# <a name="default-tls-cipher-suites-for-net-on-linux"></a><span data-ttu-id="0cbe6-103">Linux의 .NET용 기본 TLS 암호 그룹</span><span class="sxs-lookup"><span data-stu-id="0cbe6-103">Default TLS cipher suites for .NET on Linux</span></span>

<span data-ttu-id="0cbe6-104">Linux에서 .NET은 이제 <xref:System.Net.Security.SslStream> 클래스를 통해 TLS/SSL을 수행하거나 <xref:System.Net.Http.HttpClient> 클래스를 통해 HTTPS와 같은 상위 수준 작업을 수행할 때 기본 암호 그룹에 대한 OpenSSL 구성을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-104">.NET, on Linux, now respects the OpenSSL configuration for default cipher suites when doing TLS/SSL via the <xref:System.Net.Security.SslStream> class or higher-level operations, such as HTTPS via the <xref:System.Net.Http.HttpClient> class.</span></span> <span data-ttu-id="0cbe6-105">기본 암호 그룹이 명시적으로 구성되지 않은 경우 Linux의 .NET은 엄격하게 제한된 허용 암호 그룹 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-105">When default cipher suites aren't explicitly configured, .NET on Linux uses a tightly restricted list of permitted cipher suites.</span></span>

## <a name="change-description"></a><span data-ttu-id="0cbe6-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0cbe6-106">Change description</span></span>

<span data-ttu-id="0cbe6-107">이전 .NET 버전에서 .NET은 기본 암호 그룹에 대한 시스템 구성을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-107">In previous .NET versions, .NET does not respect system configuration for default cipher suites.</span></span> <span data-ttu-id="0cbe6-108">Linux의 .NET용 기본 암호 그룹 목록은 매우 관대합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-108">The default cipher suite list for .NET on Linux is very permissive.</span></span>

<span data-ttu-id="0cbe6-109">.NET 5.0부터 Linux의 .NET은 *openssl.cnf* 에 지정된 경우 기본 암호 그룹에 대한 OpenSSL 구성을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-109">Starting in .NET 5.0, .NET on Linux respects the OpenSSL configuration for default cipher suites when it's specified in *openssl.cnf*.</span></span> <span data-ttu-id="0cbe6-110">암호 그룹이 명시적으로 구성되지 않은 경우 허용되는 유일한 암호 그룹은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-110">When cipher suites aren't explicitly configured, the only permitted cipher suites are as follows:</span></span>

- <span data-ttu-id="0cbe6-111">TLS 1.3 암호 그룹</span><span class="sxs-lookup"><span data-stu-id="0cbe6-111">TLS 1.3 cipher suites</span></span>
- <span data-ttu-id="0cbe6-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="0cbe6-112">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="0cbe6-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="0cbe6-113">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="0cbe6-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="0cbe6-114">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="0cbe6-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="0cbe6-115">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="0cbe6-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="0cbe6-116">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="0cbe6-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="0cbe6-117">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span></span>
- <span data-ttu-id="0cbe6-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="0cbe6-118">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="0cbe6-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="0cbe6-119">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span>

<span data-ttu-id="0cbe6-120">이 대체 기본값에는 TLS 1.0 또는 TLS 1.1과 호환되는 암호 그룹이 포함되어 있지 않으므로 이러한 이전 프로토콜 버전은 기본적으로 효과적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-120">Since this fallback default doesn't include any cipher suites that are compatible with TLS 1.0 or TLS 1.1, these older protocol versions are effectively disabled by default.</span></span>

<span data-ttu-id="0cbe6-121">특정 세션에 대해 SslStream에 CipherSuitePolicy 값을 제공하면 구성 파일 콘텐츠 및/또는 .NET 대체 기본값이 계속 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-121">Supplying a CipherSuitePolicy value to SslStream for a specific session will still replace the configuration file content and/or .NET fallback default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0cbe6-122">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0cbe6-122">Reason for change</span></span>

<span data-ttu-id="0cbe6-123">Linux에서 .NET을 실행하는 사용자가 <xref:System.Net.Security.SslStream>의 기본 구성을 타사 평가 도구에서 높은 보안 등급을 제공했던 구성으로 변경하도록 요청했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-123">Users running .NET on Linux requested that the default configuration for <xref:System.Net.Security.SslStream> be changed to one that provided a high security rating from third-party assessment tools.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0cbe6-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0cbe6-124">Version introduced</span></span>

<span data-ttu-id="0cbe6-125">5.0</span><span class="sxs-lookup"><span data-stu-id="0cbe6-125">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0cbe6-126">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0cbe6-126">Recommended action</span></span>

<span data-ttu-id="0cbe6-127">새로운 기본값은 최신 클라이언트 또는 서버와 통신할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-127">The new defaults are likely to work when communicating with modern clients or servers.</span></span> <span data-ttu-id="0cbe6-128">기본 암호 그룹 목록을 확장하여 레거시 클라이언트를 허용하거나 레거시 서버에 연결하는 경우 `CipherSuitePolicy` 값을 지정하거나 OpenSSL 구성 파일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-128">If you need to expand the default cipher suite list to accept legacy clients (or to contact legacy servers), either specify a `CipherSuitePolicy` value or change the OpenSSL configuration file.</span></span> <span data-ttu-id="0cbe6-129">대부분의 Linux 배포에서 OpenSSL 구성 파일은 */etc/ssl/openssl.cnf* 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-129">On many Linux distributions, the OpenSSL configuration file is at */etc/ssl/openssl.cnf*.</span></span>

<span data-ttu-id="0cbe6-130">이 샘플 *opensssl.cnf* 파일은 Linux의 .NET 5.0 이상에 대한 기본 암호 그룹 정책과 동일한 최소 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-130">This sample *openssl.cnf* file is a minimal file that's equivalent to the default cipher suites policy for .NET 5.0 and later on Linux.</span></span> <span data-ttu-id="0cbe6-131">시스템 파일을 바꾸는 대신 이러한 개념을 시스템에 있는 파일과 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-131">Instead of replacing the system file, merge these concepts with the file that's present on your system.</span></span>

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

<span data-ttu-id="0cbe6-132">Red Hat Enterprise Linux, CentOS 및 Fedora 배포에서 .NET 애플리케이션은 기본적으로 시스템 전체 암호화 정책에서 허용되는 암호 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-132">On the Red Hat Enterprise Linux, CentOS, and Fedora distributions, .NET applications default to the cipher suites permitted by the system-wide cryptographic policies.</span></span> <span data-ttu-id="0cbe6-133">이러한 배포에서는 *openssl.cnf* 대신 암호화 정책 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-133">On these distributions, use the crypto-policies configuration instead of *openssl.cnf*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0cbe6-134">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0cbe6-134">Affected APIs</span></span>

<span data-ttu-id="0cbe6-135">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cbe6-135">Not detectible via API analysis.</span></span>

<!--

### Affected APIs

- Not detectible via API analysis.

### Category

- Cryptography
- Security

-->
