---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251865"
---
# <a name="servicecertificate"></a><span data-ttu-id="e34cf-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e34cf-101">\<serviceCertificate></span></span>
<span data-ttu-id="e34cf-102">토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="e34cf-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e34cf-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e34cf-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="e34cf-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="e34cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e34cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="e34cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="e34cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e34cf-107">구문</span><span class="sxs-lookup"><span data-stu-id="e34cf-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e34cf-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e34cf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e34cf-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e34cf-110">특성</span><span class="sxs-lookup"><span data-stu-id="e34cf-110">Attributes</span></span>  
 <span data-ttu-id="e34cf-111">없음</span><span class="sxs-lookup"><span data-stu-id="e34cf-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e34cf-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e34cf-112">Child Elements</span></span>  
  
|<span data-ttu-id="e34cf-113">요소</span><span class="sxs-lookup"><span data-stu-id="e34cf-113">Element</span></span>|<span data-ttu-id="e34cf-114">Description</span><span class="sxs-lookup"><span data-stu-id="e34cf-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e34cf-115">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="e34cf-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="e34cf-116">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e34cf-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e34cf-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e34cf-118">요소</span><span class="sxs-lookup"><span data-stu-id="e34cf-118">Element</span></span>|<span data-ttu-id="e34cf-119">설명</span><span class="sxs-lookup"><span data-stu-id="e34cf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e34cf-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e34cf-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="e34cf-121"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> 및 (SAM)을 구성 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e34cf-122">예제</span><span class="sxs-lookup"><span data-stu-id="e34cf-122">Example</span></span>  
 <span data-ttu-id="e34cf-123">다음 XML에서는 \<serviceCertificate > 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="e34cf-124">XML은 `CustomToken` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e34cf-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
