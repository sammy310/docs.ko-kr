---
title: <netHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732817"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="2d38a-102">\<전송 > \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2d38a-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="2d38a-103">HTTP 전송의 인증 매개 변수를 제어하는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="2d38a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2d38a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2d38a-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="2d38a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2d38a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="2d38a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="2d38a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2d38a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="2d38a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="2d38a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2d38a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2d38a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="2d38a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**전송 >**</span><span class="sxs-lookup"><span data-stu-id="2d38a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d38a-111">구문</span><span class="sxs-lookup"><span data-stu-id="2d38a-111">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d38a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2d38a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2d38a-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d38a-114">특성</span><span class="sxs-lookup"><span data-stu-id="2d38a-114">Attributes</span></span>  
  
|<span data-ttu-id="2d38a-115">특성</span><span class="sxs-lookup"><span data-stu-id="2d38a-115">Attribute</span></span>|<span data-ttu-id="2d38a-116">설명</span><span class="sxs-lookup"><span data-stu-id="2d38a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d38a-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2d38a-117">clientCredentialType</span></span>|<span data-ttu-id="2d38a-118">-HTTP 인증을 사용 하 여 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="2d38a-119">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-119">The default is `None`.</span></span> <span data-ttu-id="2d38a-120">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="2d38a-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="2d38a-121">proxyCredentialType</span></span>|<span data-ttu-id="2d38a-122">-HTTP를 통해 프록시를 사용 하 여 도메인 내에서 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="2d38a-123">이 특성은 부모 `mode` 요소의 `security` 특성이 `Transport` 또는 `TransportCredentialsOnly`일 때만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="2d38a-124">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="2d38a-125">realm</span><span class="sxs-lookup"><span data-stu-id="2d38a-125">realm</span></span>|<span data-ttu-id="2d38a-126">다이제스트 또는 기본 인증의 HTTP 인증 체계에 사용되는 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="2d38a-127">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="2d38a-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="2d38a-128">policyEnforcement</span></span>|<span data-ttu-id="2d38a-129">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="2d38a-130">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="2d38a-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="2d38a-131">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="2d38a-132">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="2d38a-133">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="2d38a-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="2d38a-134">protectionScenario</span></span>|<span data-ttu-id="2d38a-135">이 열거형은 정책을 통해 적용되는 보호 시나리오를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2d38a-136">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="2d38a-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2d38a-137">값</span><span class="sxs-lookup"><span data-stu-id="2d38a-137">Value</span></span>|<span data-ttu-id="2d38a-138">설명</span><span class="sxs-lookup"><span data-stu-id="2d38a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d38a-139">없음</span><span class="sxs-lookup"><span data-stu-id="2d38a-139">None</span></span>|<span data-ttu-id="2d38a-140">메시지가 전송 중에 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2d38a-141">Basic</span><span class="sxs-lookup"><span data-stu-id="2d38a-141">Basic</span></span>|<span data-ttu-id="2d38a-142">기본 인증을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="2d38a-143">Digest</span><span class="sxs-lookup"><span data-stu-id="2d38a-143">Digest</span></span>|<span data-ttu-id="2d38a-144">다이제스트 인증을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="2d38a-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2d38a-145">Ntlm</span></span>|<span data-ttu-id="2d38a-146">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2d38a-147">창</span><span class="sxs-lookup"><span data-stu-id="2d38a-147">Windows</span></span>|<span data-ttu-id="2d38a-148">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="2d38a-149">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="2d38a-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2d38a-150">값</span><span class="sxs-lookup"><span data-stu-id="2d38a-150">Value</span></span>|<span data-ttu-id="2d38a-151">설명</span><span class="sxs-lookup"><span data-stu-id="2d38a-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d38a-152">없음</span><span class="sxs-lookup"><span data-stu-id="2d38a-152">None</span></span>|<span data-ttu-id="2d38a-153">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2d38a-154">Basic</span><span class="sxs-lookup"><span data-stu-id="2d38a-154">Basic</span></span>|<span data-ttu-id="2d38a-155">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2d38a-156">Digest</span><span class="sxs-lookup"><span data-stu-id="2d38a-156">Digest</span></span>|<span data-ttu-id="2d38a-157">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="2d38a-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2d38a-158">Ntlm</span></span>|<span data-ttu-id="2d38a-159">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="2d38a-160">창</span><span class="sxs-lookup"><span data-stu-id="2d38a-160">Windows</span></span>|<span data-ttu-id="2d38a-161">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="2d38a-162">인증서</span><span class="sxs-lookup"><span data-stu-id="2d38a-162">Certificate</span></span>|<span data-ttu-id="2d38a-163">인증서를 사용하여 클라이언트 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="2d38a-164">이 옵션은 부모 `Mode` 요소의 `security` 특성이 Transport로 설정되어 있을 때만 작동하며 TransportCredentialOnly로 설정된 경우에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d38a-165">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2d38a-165">Child Elements</span></span>  
 <span data-ttu-id="2d38a-166">없음</span><span class="sxs-lookup"><span data-stu-id="2d38a-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d38a-167">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2d38a-167">Parent Elements</span></span>  
  
|<span data-ttu-id="2d38a-168">요소</span><span class="sxs-lookup"><span data-stu-id="2d38a-168">Element</span></span>|<span data-ttu-id="2d38a-169">설명</span><span class="sxs-lookup"><span data-stu-id="2d38a-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d38a-170">\<security ></span><span class="sxs-lookup"><span data-stu-id="2d38a-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="2d38a-171">[\<netHttpBinding >](nethttpbinding.md)에 대 한 보안 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d38a-172">예제</span><span class="sxs-lookup"><span data-stu-id="2d38a-172">Example</span></span>  
 <span data-ttu-id="2d38a-173">다음 예제에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="2d38a-174">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2d38a-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="2d38a-175">참조</span><span class="sxs-lookup"><span data-stu-id="2d38a-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="2d38a-176">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2d38a-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2d38a-177">바인딩</span><span class="sxs-lookup"><span data-stu-id="2d38a-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2d38a-178">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="2d38a-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2d38a-179">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2d38a-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2d38a-180">\<binding ></span><span class="sxs-lookup"><span data-stu-id="2d38a-180">\<binding></span></span>](bindings.md)
