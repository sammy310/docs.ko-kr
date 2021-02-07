---
description: 다음에 대해 자세히 알아보세요. <serviceCertificate>
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: d9940fd96667211b1f9fd672b824af84e0d5143a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725326"
---
# \<serviceCertificate>

<span data-ttu-id="2b2b1-102">토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="2b2b1-103">구문</span><span class="sxs-lookup"><span data-stu-id="2b2b1-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b2b1-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2b2b1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="2b2b1-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b2b1-106">특성</span><span class="sxs-lookup"><span data-stu-id="2b2b1-106">Attributes</span></span>  

 <span data-ttu-id="2b2b1-107">None</span><span class="sxs-lookup"><span data-stu-id="2b2b1-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b2b1-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2b2b1-108">Child Elements</span></span>  
  
|<span data-ttu-id="2b2b1-109">요소</span><span class="sxs-lookup"><span data-stu-id="2b2b1-109">Element</span></span>|<span data-ttu-id="2b2b1-110">설명</span><span class="sxs-lookup"><span data-stu-id="2b2b1-110">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="2b2b1-111">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b1-111">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b2b1-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2b2b1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="2b2b1-113">요소</span><span class="sxs-lookup"><span data-stu-id="2b2b1-113">Element</span></span>|<span data-ttu-id="2b2b1-114">설명</span><span class="sxs-lookup"><span data-stu-id="2b2b1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="2b2b1-115"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 (SAM)을 구성 하는 설정을 포함 합니다 <xref:System.IdentityModel.Services.SessionAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="2b2b1-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b2b1-116">예제</span><span class="sxs-lookup"><span data-stu-id="2b2b1-116">Example</span></span>  

 <span data-ttu-id="2b2b1-117">다음 XML에서는 요소를 사용 하는 방법을 보여 줍니다 \<serviceCertificate> .</span><span class="sxs-lookup"><span data-stu-id="2b2b1-117">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="2b2b1-118">XML은 샘플에서 가져옵니다 `CustomToken` .</span><span class="sxs-lookup"><span data-stu-id="2b2b1-118">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
