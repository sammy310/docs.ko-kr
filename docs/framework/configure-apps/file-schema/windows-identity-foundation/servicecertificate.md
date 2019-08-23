---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942408"
---
# <a name="servicecertificate"></a><span data-ttu-id="58c57-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="58c57-101">\<serviceCertificate></span></span>
<span data-ttu-id="58c57-102">토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="58c57-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="58c57-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="58c57-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="58c57-104">\<federationConfiguration></span></span>  
<span data-ttu-id="58c57-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="58c57-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c57-106">구문</span><span class="sxs-lookup"><span data-stu-id="58c57-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58c57-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="58c57-107">Attributes and Elements</span></span>  
 <span data-ttu-id="58c57-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58c57-109">특성</span><span class="sxs-lookup"><span data-stu-id="58c57-109">Attributes</span></span>  
 <span data-ttu-id="58c57-110">없음</span><span class="sxs-lookup"><span data-stu-id="58c57-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="58c57-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="58c57-111">Child Elements</span></span>  
  
|<span data-ttu-id="58c57-112">요소</span><span class="sxs-lookup"><span data-stu-id="58c57-112">Element</span></span>|<span data-ttu-id="58c57-113">Description</span><span class="sxs-lookup"><span data-stu-id="58c57-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58c57-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="58c57-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="58c57-115">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58c57-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="58c57-116">Parent Elements</span></span>  
  
|<span data-ttu-id="58c57-117">요소</span><span class="sxs-lookup"><span data-stu-id="58c57-117">Element</span></span>|<span data-ttu-id="58c57-118">Description</span><span class="sxs-lookup"><span data-stu-id="58c57-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58c57-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="58c57-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="58c57-120"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> 및 (SAM)을 구성 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58c57-121">예제</span><span class="sxs-lookup"><span data-stu-id="58c57-121">Example</span></span>  
 <span data-ttu-id="58c57-122">다음 XML에서는 \<serviceCertificate > 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="58c57-123">XML은 `CustomToken` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="58c57-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
