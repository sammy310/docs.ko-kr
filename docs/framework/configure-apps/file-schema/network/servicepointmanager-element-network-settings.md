---
title: <servicePointManager> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089121"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="43b13-102">\<servicePointManager> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="43b13-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="43b13-103">네트워크 리소스에 대 한 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-103">Configures connections to network resources.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**

## <a name="syntax"></a><span data-ttu-id="43b13-104">구문</span><span class="sxs-lookup"><span data-stu-id="43b13-104">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43b13-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="43b13-105">Attributes and Elements</span></span>  
 <span data-ttu-id="43b13-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43b13-107">특성</span><span class="sxs-lookup"><span data-stu-id="43b13-107">Attributes</span></span>  
  
|<span data-ttu-id="43b13-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="43b13-108">**Attribute**</span></span>|<span data-ttu-id="43b13-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="43b13-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="43b13-110">인증서를 사용 하기 전에 시스템에서 인증서의 이름이 서버 호스트 이름과 일치 하는지 확인 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-110">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="43b13-111">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-111">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="43b13-112">인증서를 사용 하기 전에 시스템에서 인증서가 해지 되었는지 여부를 확인 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-112">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="43b13-113">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-113">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="43b13-114">Dns 라운드 로빈 옵션과 함께 DNS (Domain Name Service) 확인이 캐시 되는 시간 (밀리초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-114">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="43b13-115">기본값은 120,000밀리초(2분)입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-115">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="43b13-116">IP (인터넷 프로토콜) 주소가 여러 개인 호스트 이름에 대 한 DNS 확인이 모든 주소를 반환할지 아니면 첫 번째 주소를 반환할지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-116">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="43b13-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-117">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="43b13-118">인스턴스의 SSL/TLS 세션에 적용 되는 암호화 정책을 지정 합니다 <xref:System.Net.ServicePointManager> .</span><span class="sxs-lookup"><span data-stu-id="43b13-118">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="43b13-119">가능한 값은 열거형의 값과 동일 합니다 <xref:System.Net.Security.EncryptionPolicy> .</span><span class="sxs-lookup"><span data-stu-id="43b13-119">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="43b13-120"><xref:System.Security.Authentication.CipherAlgorithmType.Null>암호화 정책이로 설정 된 경우에는를 사용 해야 합니다 `NoEncryption` .</span><span class="sxs-lookup"><span data-stu-id="43b13-120">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="43b13-121">기본값은 `RequireEncryption`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-121">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="43b13-122">POST 메서드가 서버에서 응답을 받을 것으로 간주 하는지 여부를 지정 합니다 `100-continue` .</span><span class="sxs-lookup"><span data-stu-id="43b13-122">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="43b13-123">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-123">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="43b13-124">서비스 지점 관리자에서 제어 하는 연결에 Nagle 알고리즘을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-124">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="43b13-125">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-125">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43b13-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="43b13-126">Child Elements</span></span>  
 <span data-ttu-id="43b13-127">없음</span><span class="sxs-lookup"><span data-stu-id="43b13-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43b13-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="43b13-128">Parent Elements</span></span>  
  
|<span data-ttu-id="43b13-129">**요소**</span><span class="sxs-lookup"><span data-stu-id="43b13-129">**Element**</span></span>|<span data-ttu-id="43b13-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="43b13-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="43b13-131">설정</span><span class="sxs-lookup"><span data-stu-id="43b13-131">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="43b13-132"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-132">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43b13-133">설명</span><span class="sxs-lookup"><span data-stu-id="43b13-133">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="43b13-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="43b13-134">Configuration Files</span></span>  
 <span data-ttu-id="43b13-135">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43b13-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b13-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43b13-136">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="43b13-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="43b13-137">Network Settings Schema</span></span>](index.md)
