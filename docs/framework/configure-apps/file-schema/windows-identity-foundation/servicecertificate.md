---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251865"
---
# \<serviceCertificate>
<span data-ttu-id="ef931-101">토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef931-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ef931-102">구문</span><span class="sxs-lookup"><span data-stu-id="ef931-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef931-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ef931-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ef931-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef931-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef931-105">특성</span><span class="sxs-lookup"><span data-stu-id="ef931-105">Attributes</span></span>  
 <span data-ttu-id="ef931-106">None</span><span class="sxs-lookup"><span data-stu-id="ef931-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef931-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ef931-107">Child Elements</span></span>  
  
|<span data-ttu-id="ef931-108">요소</span><span class="sxs-lookup"><span data-stu-id="ef931-108">Element</span></span>|<span data-ttu-id="ef931-109">Description</span><span class="sxs-lookup"><span data-stu-id="ef931-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="ef931-110">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef931-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef931-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ef931-111">Parent Elements</span></span>  
  
|<span data-ttu-id="ef931-112">요소</span><span class="sxs-lookup"><span data-stu-id="ef931-112">Element</span></span>|<span data-ttu-id="ef931-113">Description</span><span class="sxs-lookup"><span data-stu-id="ef931-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="ef931-114"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 (SAM)을 구성 하는 설정을 포함 합니다 <xref:System.IdentityModel.Services.SessionAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="ef931-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ef931-115">예제</span><span class="sxs-lookup"><span data-stu-id="ef931-115">Example</span></span>  
 <span data-ttu-id="ef931-116">다음 XML에서는 요소를 사용 하는 방법을 보여 줍니다 \<serviceCertificate> .</span><span class="sxs-lookup"><span data-stu-id="ef931-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="ef931-117">XML은 샘플에서 가져옵니다 `CustomToken` .</span><span class="sxs-lookup"><span data-stu-id="ef931-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
