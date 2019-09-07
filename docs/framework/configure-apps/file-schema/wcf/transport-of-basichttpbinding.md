---
title: <basicHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: 2cf69c48a51ce2c687ebcfe9f87f7c22f5f86084
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399378"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="e65d3-102">\<basicHttpBinding >의 \<전송 ></span><span class="sxs-lookup"><span data-stu-id="e65d3-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="e65d3-103">HTTP 전송의 인증 매개 변수를 제어하는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="e65d3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e65d3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e65d3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e65d3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e65d3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e65d3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e65d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<basicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e65d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="e65d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="e65d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e65d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<보안 >** ](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e65d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="e65d3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<전송 >**</span><span class="sxs-lookup"><span data-stu-id="e65d3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65d3-111">구문</span><span class="sxs-lookup"><span data-stu-id="e65d3-111">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e65d3-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e65d3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e65d3-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e65d3-114">특성</span><span class="sxs-lookup"><span data-stu-id="e65d3-114">Attributes</span></span>  
  
|<span data-ttu-id="e65d3-115">특성</span><span class="sxs-lookup"><span data-stu-id="e65d3-115">Attribute</span></span>|<span data-ttu-id="e65d3-116">Description</span><span class="sxs-lookup"><span data-stu-id="e65d3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e65d3-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e65d3-117">clientCredentialType</span></span>|<span data-ttu-id="e65d3-118">-HTTP 인증을 사용 하 여 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="e65d3-119">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-119">The default is `None`.</span></span> <span data-ttu-id="e65d3-120">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="e65d3-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e65d3-121">proxyCredentialType</span></span>|<span data-ttu-id="e65d3-122">-HTTP를 통해 프록시를 사용 하 여 도메인 내에서 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="e65d3-123">이 특성은 부모 `mode` 요소의 `security` 특성이 `Transport` 또는 `TransportCredentialsOnly`일 때만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="e65d3-124">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="e65d3-125">realm</span><span class="sxs-lookup"><span data-stu-id="e65d3-125">realm</span></span>|<span data-ttu-id="e65d3-126">다이제스트 또는 기본 인증의 HTTP 인증 체계에 사용되는 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="e65d3-127">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="e65d3-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="e65d3-128">policyEnforcement</span></span>|<span data-ttu-id="e65d3-129">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e65d3-130">1.  Never - 정책이 적용되지 않습니다(확장 보호가 사용되지 않음).</span><span class="sxs-lookup"><span data-stu-id="e65d3-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e65d3-131">2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e65d3-132">3.  Always – 정책이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e65d3-133">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="e65d3-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="e65d3-134">protectionScenario</span></span>|<span data-ttu-id="e65d3-135">이 열거형은 정책을 통해 적용되는 보호 시나리오를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e65d3-136">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="e65d3-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e65d3-137">값</span><span class="sxs-lookup"><span data-stu-id="e65d3-137">Value</span></span>|<span data-ttu-id="e65d3-138">설명</span><span class="sxs-lookup"><span data-stu-id="e65d3-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e65d3-139">없음</span><span class="sxs-lookup"><span data-stu-id="e65d3-139">None</span></span>|<span data-ttu-id="e65d3-140">메시지가 전송 중에 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e65d3-141">Basic</span><span class="sxs-lookup"><span data-stu-id="e65d3-141">Basic</span></span>|<span data-ttu-id="e65d3-142">기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="e65d3-143">Digest</span><span class="sxs-lookup"><span data-stu-id="e65d3-143">Digest</span></span>|<span data-ttu-id="e65d3-144">다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="e65d3-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e65d3-145">Ntlm</span></span>|<span data-ttu-id="e65d3-146">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e65d3-147">Windows</span><span class="sxs-lookup"><span data-stu-id="e65d3-147">Windows</span></span>|<span data-ttu-id="e65d3-148">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e65d3-149">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="e65d3-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e65d3-150">값</span><span class="sxs-lookup"><span data-stu-id="e65d3-150">Value</span></span>|<span data-ttu-id="e65d3-151">설명</span><span class="sxs-lookup"><span data-stu-id="e65d3-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e65d3-152">없음</span><span class="sxs-lookup"><span data-stu-id="e65d3-152">None</span></span>|<span data-ttu-id="e65d3-153">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e65d3-154">Basic</span><span class="sxs-lookup"><span data-stu-id="e65d3-154">Basic</span></span>|<span data-ttu-id="e65d3-155">RFC 2617 – HTTP 인증에 정의 된 대로 기본 인증을 지정 합니다. 기본 및 다이제스트 인증.</span><span class="sxs-lookup"><span data-stu-id="e65d3-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e65d3-156">Digest</span><span class="sxs-lookup"><span data-stu-id="e65d3-156">Digest</span></span>|<span data-ttu-id="e65d3-157">RFC 2617 – HTTP 인증에 정의 된 대로 다이제스트 인증을 지정 합니다. 기본 및 다이제스트 인증.</span><span class="sxs-lookup"><span data-stu-id="e65d3-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e65d3-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e65d3-158">Ntlm</span></span>|<span data-ttu-id="e65d3-159">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e65d3-160">Windows</span><span class="sxs-lookup"><span data-stu-id="e65d3-160">Windows</span></span>|<span data-ttu-id="e65d3-161">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="e65d3-162">Certificate</span><span class="sxs-lookup"><span data-stu-id="e65d3-162">Certificate</span></span>|<span data-ttu-id="e65d3-163">인증서를 사용하여 클라이언트 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="e65d3-164">이 옵션은 부모 `Mode` 요소의 `security` 특성이 Transport로 설정되어 있을 때만 작동하며 TransportCredentialOnly로 설정된 경우에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e65d3-165">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e65d3-165">Child Elements</span></span>  
 <span data-ttu-id="e65d3-166">없음</span><span class="sxs-lookup"><span data-stu-id="e65d3-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e65d3-167">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e65d3-167">Parent Elements</span></span>  
  
|<span data-ttu-id="e65d3-168">요소</span><span class="sxs-lookup"><span data-stu-id="e65d3-168">Element</span></span>|<span data-ttu-id="e65d3-169">설명</span><span class="sxs-lookup"><span data-stu-id="e65d3-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e65d3-170">\<security></span><span class="sxs-lookup"><span data-stu-id="e65d3-170">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="e65d3-171">[ \<BasicHttpBinding >](basichttpbinding.md)의 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-171">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e65d3-172">예제</span><span class="sxs-lookup"><span data-stu-id="e65d3-172">Example</span></span>  
 <span data-ttu-id="e65d3-173">다음 예제에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="e65d3-174">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e65d3-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="e65d3-175">참고자료</span><span class="sxs-lookup"><span data-stu-id="e65d3-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="e65d3-176">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e65d3-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e65d3-177">바인딩</span><span class="sxs-lookup"><span data-stu-id="e65d3-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e65d3-178">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="e65d3-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e65d3-179">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="e65d3-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e65d3-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="e65d3-180">\<binding></span></span>](../../../misc/binding.md)
