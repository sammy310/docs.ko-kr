---
title: <message> 의 요소 <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
ms.openlocfilehash: ab767a5a1179de81bf9a8adc61799ede2d915ac1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204907"
---
# <a name="message-element-of-nettcpbinding"></a><span data-ttu-id="25d3b-102">\<message> 의 요소 \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="25d3b-102">\<message> element of \<netTcpBinding></span></span>

<span data-ttu-id="25d3b-103">로 구성 된 끝점의 메시지 수준 보안 요구 사항 형식을 정의 합니다 [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="25d3b-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="25d3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="25d3b-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="System.Servicemodel.Security.SecurityAlgorithmsuite"
         clientCredentialType="None/Windows/UserName/Certificate/IssuedToken" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25d3b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="25d3b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="25d3b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25d3b-107">특성</span><span class="sxs-lookup"><span data-stu-id="25d3b-107">Attributes</span></span>  
  
|<span data-ttu-id="25d3b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="25d3b-108">Attribute</span></span>|<span data-ttu-id="25d3b-109">설명</span><span class="sxs-lookup"><span data-stu-id="25d3b-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="25d3b-110">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-110">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="25d3b-111">알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-111">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="25d3b-112">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-112">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="25d3b-113">가능한 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-113">Possible values are shown in the following table.</span></span> <span data-ttu-id="25d3b-114">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-114">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="25d3b-115">서비스 바인딩에서 기본값과 같지 않은 `algorithmSuite` 값을 지정하는 경우 Svcutil.exe을 사용하여 구성 파일을 생성하면 파일이 제대로 생성되지 않으므로 구성 파일을 수동으로 편집하여 이 특성을 원하는 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-115">If the service binding specifies an `algorithmSuite` value that is not equal to the default, and you generate the configuration file using Svcutil.exe, then it is not generated correctly, and you must manually edit the configuration file to set this attribute to the desired value.</span></span>|  
|`clientCredentialType`|<span data-ttu-id="25d3b-116">메시지 기반 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-116">Specifies the type of credential to be used when performing client authentication using Message-based security.</span></span> <span data-ttu-id="25d3b-117">가능한 값은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-117">Possible values are shown in the following table.</span></span> <span data-ttu-id="25d3b-118">기본값은 `UserName`입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-118">The default value is `UserName`.</span></span> <span data-ttu-id="25d3b-119">이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-119">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="25d3b-120">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="25d3b-120">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="25d3b-121">Value</span><span class="sxs-lookup"><span data-stu-id="25d3b-121">Value</span></span>|<span data-ttu-id="25d3b-122">설명</span><span class="sxs-lookup"><span data-stu-id="25d3b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="25d3b-123">Basic128</span><span class="sxs-lookup"><span data-stu-id="25d3b-123">Basic128</span></span>|<span data-ttu-id="25d3b-124">Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-124">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-125">Basic192</span><span class="sxs-lookup"><span data-stu-id="25d3b-125">Basic192</span></span>|<span data-ttu-id="25d3b-126">Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-126">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-127">Basic256</span><span class="sxs-lookup"><span data-stu-id="25d3b-127">Basic256</span></span>|<span data-ttu-id="25d3b-128">Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-128">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-129">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-129">Basic256Rsa15</span></span>|<span data-ttu-id="25d3b-130">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-130">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-131">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-131">Basic192Rsa15</span></span>|<span data-ttu-id="25d3b-132">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-132">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-133">TripleDes</span><span class="sxs-lookup"><span data-stu-id="25d3b-133">TripleDes</span></span>|<span data-ttu-id="25d3b-134">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-134">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-135">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-135">Basic128Rsa15</span></span>|<span data-ttu-id="25d3b-136">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-136">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-137">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-137">TripleDesRsa15</span></span>|<span data-ttu-id="25d3b-138">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-138">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-139">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="25d3b-139">Basic128Sha256</span></span>|<span data-ttu-id="25d3b-140">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-140">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-141">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="25d3b-141">Basic192Sha256</span></span>|<span data-ttu-id="25d3b-142">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-142">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-143">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="25d3b-143">Basic256Sha256</span></span>|<span data-ttu-id="25d3b-144">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-144">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-145">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="25d3b-145">TripleDesSha256</span></span>|<span data-ttu-id="25d3b-146">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-146">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-147">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-147">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="25d3b-148">메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-148">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-149">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-149">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="25d3b-150">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-150">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-151">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-151">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="25d3b-152">메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-152">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="25d3b-153">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="25d3b-153">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="25d3b-154">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-154">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="25d3b-155">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="25d3b-155">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="25d3b-156">Value</span><span class="sxs-lookup"><span data-stu-id="25d3b-156">Value</span></span>|<span data-ttu-id="25d3b-157">설명</span><span class="sxs-lookup"><span data-stu-id="25d3b-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="25d3b-158">없음</span><span class="sxs-lookup"><span data-stu-id="25d3b-158">None</span></span>|<span data-ttu-id="25d3b-159">이를 통해 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-159">This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="25d3b-160">서비스 쪽에서는 서비스가 클라이언트 자격 증명을 요구하지 않음을 의미하고</span><span class="sxs-lookup"><span data-stu-id="25d3b-160">On the service, this indicates that the service does not require any client credential.</span></span> <span data-ttu-id="25d3b-161">클라이언트 쪽에서는 클라이언트가 클라이언트 자격 증명을 제공하지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-161">On the client, this indicates that the client does not provide any client credential.</span></span>|  
|<span data-ttu-id="25d3b-162">Windows</span><span class="sxs-lookup"><span data-stu-id="25d3b-162">Windows</span></span>|<span data-ttu-id="25d3b-163">Windows 자격 증명의 인증된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-163">Allows the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span>|  
|<span data-ttu-id="25d3b-164">UserName</span><span class="sxs-lookup"><span data-stu-id="25d3b-164">UserName</span></span>|<span data-ttu-id="25d3b-165">서비스에서 UserName 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-165">Allows the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="25d3b-166">WCF에서는 암호 다이제스트를 보내거나 암호를 사용 하 고 메시지 보안에 이러한 키를 사용 하 여 키를 파생 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-166">WCF does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="25d3b-167">따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-167">As such, WCF enforces that the transport is secured when using UserName credentials.</span></span> <span data-ttu-id="25d3b-168">이 자격 증명 모드에서는 상호 운용이 가능한 교환 또는 `negotiateServiceCredential` 특성을 기반으로 하는 상호 운용이 불가능한 협상이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-168">This credential mode results in either an interoperable exchange or a non-interoperable negotiation based on the `negotiateServiceCredential` attribute.</span></span>|  
|<span data-ttu-id="25d3b-169">인증서</span><span class="sxs-lookup"><span data-stu-id="25d3b-169">Certificate</span></span>|<span data-ttu-id="25d3b-170">서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-170">Allows the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="25d3b-171">메시지 보안 모드가 사용되고 `negotiateServiceCredential` 특성이 `false`로 설정되면 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-171">If message security mode is used and the `negotiateServiceCredential` attribute is set to `false`, the client must be provisioned with the service certificate.</span></span>|  
|<span data-ttu-id="25d3b-172">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="25d3b-172">IssuedToken</span></span>|<span data-ttu-id="25d3b-173">일반적으로 STS(보안 토큰 서비스)에서 발급하는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-173">Specifies a custom token, usually issued by a Security Token Service (STS).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25d3b-174">자식 요소</span><span class="sxs-lookup"><span data-stu-id="25d3b-174">Child Elements</span></span>  

 <span data-ttu-id="25d3b-175">없음</span><span class="sxs-lookup"><span data-stu-id="25d3b-175">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25d3b-176">부모 요소</span><span class="sxs-lookup"><span data-stu-id="25d3b-176">Parent Elements</span></span>  
  
|<span data-ttu-id="25d3b-177">요소</span><span class="sxs-lookup"><span data-stu-id="25d3b-177">Element</span></span>|<span data-ttu-id="25d3b-178">설명</span><span class="sxs-lookup"><span data-stu-id="25d3b-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="25d3b-179"><xref:System.ServiceModel.Configuration.NetTcpBindingElement>의 보안 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-179">Defines the security capabilities for the <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25d3b-180">설명</span><span class="sxs-lookup"><span data-stu-id="25d3b-180">Remarks</span></span>  

 <span data-ttu-id="25d3b-181">Message는 SOAP 메시지 무결성 및 기밀성과 통신 피어의 상호 인증을 위해 메시지 수준 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-181">Message uses message-level security for the integrity and confidentiality of the SOAP message, and for mutual authentication of the communication peers.</span></span> <span data-ttu-id="25d3b-182">바인딩에서이 보안 모드를 선택 하면 채널 스택은 메시지 보안 바인딩 요소를 사용 하 여 구성 되 고 SOAP 메시지는 WS-SECURITY \* 표준과 호환 되는 보안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3b-182">If this security mode is selected on a binding, the channel stack is configured with message security binding elements and the SOAP messages are secured in compliance with WS-Security\* standards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d3b-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25d3b-183">See also</span></span>

- <xref:System.ServiceModel.MessageSecurityOverTcp>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="25d3b-184">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="25d3b-184">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="25d3b-185">바인딩하</span><span class="sxs-lookup"><span data-stu-id="25d3b-185">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="25d3b-186">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="25d3b-186">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="25d3b-187">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="25d3b-187">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
