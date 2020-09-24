---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: ce8be6eea5469b099a368a0b62e791faa7e3cbfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156994"
---
# \<serviceCertificate>

<span data-ttu-id="a4df4-101">토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="a4df4-102">구문</span><span class="sxs-lookup"><span data-stu-id="a4df4-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4df4-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a4df4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a4df4-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4df4-105">특성</span><span class="sxs-lookup"><span data-stu-id="a4df4-105">Attributes</span></span>  

 <span data-ttu-id="a4df4-106">없음</span><span class="sxs-lookup"><span data-stu-id="a4df4-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4df4-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a4df4-107">Child Elements</span></span>  
  
|<span data-ttu-id="a4df4-108">요소</span><span class="sxs-lookup"><span data-stu-id="a4df4-108">Element</span></span>|<span data-ttu-id="a4df4-109">설명</span><span class="sxs-lookup"><span data-stu-id="a4df4-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="a4df4-110">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4df4-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a4df4-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a4df4-112">요소</span><span class="sxs-lookup"><span data-stu-id="a4df4-112">Element</span></span>|<span data-ttu-id="a4df4-113">설명</span><span class="sxs-lookup"><span data-stu-id="a4df4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="a4df4-114"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) 및 (SAM)을 구성 하는 설정을 포함 합니다 <xref:System.IdentityModel.Services.SessionAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="a4df4-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a4df4-115">예제</span><span class="sxs-lookup"><span data-stu-id="a4df4-115">Example</span></span>  

 <span data-ttu-id="a4df4-116">다음 XML에서는 요소를 사용 하는 방법을 보여 줍니다 \<serviceCertificate> .</span><span class="sxs-lookup"><span data-stu-id="a4df4-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="a4df4-117">XML은 샘플에서 가져옵니다 `CustomToken` .</span><span class="sxs-lookup"><span data-stu-id="a4df4-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
