---
description: '다음에 대 한 자세한 정보:: <transport><netHttpBinding>'
title: <netHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 1c2029fcbc57632b828fa180ba0ffbbf6b974775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773513"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="7bdc1-103">\<netHttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="7bdc1-103">\<transport> of \<netHttpBinding></span></span>

<span data-ttu-id="7bdc1-104">HTTP 전송의 인증 매개 변수를 제어하는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-104">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="7bdc1-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bdc1-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bdc1-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7bdc1-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bdc1-108">특성</span><span class="sxs-lookup"><span data-stu-id="7bdc1-108">Attributes</span></span>  
  
|<span data-ttu-id="7bdc1-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7bdc1-109">Attribute</span></span>|<span data-ttu-id="7bdc1-110">설명</span><span class="sxs-lookup"><span data-stu-id="7bdc1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7bdc1-111">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7bdc1-111">clientCredentialType</span></span>|<span data-ttu-id="7bdc1-112">-HTTP 인증을 사용 하 여 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-112">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="7bdc1-113">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-113">The default is `None`.</span></span> <span data-ttu-id="7bdc1-114">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-114">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="7bdc1-115">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="7bdc1-115">proxyCredentialType</span></span>|<span data-ttu-id="7bdc1-116">-HTTP를 통해 프록시를 사용 하 여 도메인 내에서 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-116">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="7bdc1-117">이 특성은 부모 `mode` 요소의 `security` 특성이 `Transport` 또는 `TransportCredentialsOnly`일 때만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-117">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="7bdc1-118">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-118">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="7bdc1-119">realm</span><span class="sxs-lookup"><span data-stu-id="7bdc1-119">realm</span></span>|<span data-ttu-id="7bdc1-120">다이제스트 또는 기본 인증의 HTTP 인증 체계에 사용되는 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-120">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="7bdc1-121">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="7bdc1-122">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="7bdc1-122">policyEnforcement</span></span>|<span data-ttu-id="7bdc1-123">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-123">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7bdc1-124">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="7bdc1-124">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7bdc1-125">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-125">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7bdc1-126">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-126">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7bdc1-127">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-127">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="7bdc1-128">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="7bdc1-128">protectionScenario</span></span>|<span data-ttu-id="7bdc1-129">이 열거형은 정책을 통해 적용되는 보호 시나리오를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-129">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7bdc1-130">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7bdc1-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7bdc1-131">값</span><span class="sxs-lookup"><span data-stu-id="7bdc1-131">Value</span></span>|<span data-ttu-id="7bdc1-132">설명</span><span class="sxs-lookup"><span data-stu-id="7bdc1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bdc1-133">없음</span><span class="sxs-lookup"><span data-stu-id="7bdc1-133">None</span></span>|<span data-ttu-id="7bdc1-134">메시지가 전송 중에 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-134">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7bdc1-135">Basic</span><span class="sxs-lookup"><span data-stu-id="7bdc1-135">Basic</span></span>|<span data-ttu-id="7bdc1-136">기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-136">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="7bdc1-137">다이제스트</span><span class="sxs-lookup"><span data-stu-id="7bdc1-137">Digest</span></span>|<span data-ttu-id="7bdc1-138">다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-138">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="7bdc1-139">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7bdc1-139">Ntlm</span></span>|<span data-ttu-id="7bdc1-140">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-140">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="7bdc1-141">Windows</span><span class="sxs-lookup"><span data-stu-id="7bdc1-141">Windows</span></span>|<span data-ttu-id="7bdc1-142">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-142">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="7bdc1-143">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="7bdc1-143">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7bdc1-144">값</span><span class="sxs-lookup"><span data-stu-id="7bdc1-144">Value</span></span>|<span data-ttu-id="7bdc1-145">설명</span><span class="sxs-lookup"><span data-stu-id="7bdc1-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7bdc1-146">없음</span><span class="sxs-lookup"><span data-stu-id="7bdc1-146">None</span></span>|<span data-ttu-id="7bdc1-147">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-147">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="7bdc1-148">Basic</span><span class="sxs-lookup"><span data-stu-id="7bdc1-148">Basic</span></span>|<span data-ttu-id="7bdc1-149">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-149">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="7bdc1-150">다이제스트</span><span class="sxs-lookup"><span data-stu-id="7bdc1-150">Digest</span></span>|<span data-ttu-id="7bdc1-151">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-151">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="7bdc1-152">Ntlm</span><span class="sxs-lookup"><span data-stu-id="7bdc1-152">Ntlm</span></span>|<span data-ttu-id="7bdc1-153">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-153">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="7bdc1-154">Windows</span><span class="sxs-lookup"><span data-stu-id="7bdc1-154">Windows</span></span>|<span data-ttu-id="7bdc1-155">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-155">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="7bdc1-156">인증서</span><span class="sxs-lookup"><span data-stu-id="7bdc1-156">Certificate</span></span>|<span data-ttu-id="7bdc1-157">인증서를 사용하여 클라이언트 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-157">Performs client authentication using a certificate.</span></span> <span data-ttu-id="7bdc1-158">이 옵션은 부모 `Mode` 요소의 `security` 특성이 Transport로 설정되어 있을 때만 작동하며 TransportCredentialOnly로 설정된 경우에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-158">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bdc1-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc1-159">Child Elements</span></span>  

 <span data-ttu-id="7bdc1-160">없음</span><span class="sxs-lookup"><span data-stu-id="7bdc1-160">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bdc1-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc1-161">Parent Elements</span></span>  
  
|<span data-ttu-id="7bdc1-162">요소</span><span class="sxs-lookup"><span data-stu-id="7bdc1-162">Element</span></span>|<span data-ttu-id="7bdc1-163">설명</span><span class="sxs-lookup"><span data-stu-id="7bdc1-163">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="7bdc1-164">의 보안 기능을 정의 합니다 [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="7bdc1-164">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7bdc1-165">예제</span><span class="sxs-lookup"><span data-stu-id="7bdc1-165">Example</span></span>  

 <span data-ttu-id="7bdc1-166">다음 예제에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-166">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="7bdc1-167">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc1-167">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7bdc1-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bdc1-168">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="7bdc1-169">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="7bdc1-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7bdc1-170">바인딩</span><span class="sxs-lookup"><span data-stu-id="7bdc1-170">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7bdc1-171">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7bdc1-171">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7bdc1-172">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7bdc1-172">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
