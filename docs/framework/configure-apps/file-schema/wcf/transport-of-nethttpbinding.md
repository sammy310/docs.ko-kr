---
title: <netHttpBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 996b3655b0698595256c9a7197f705d46e6e9fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169819"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="b4a27-102">\<netHttpBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="b4a27-102">\<transport> of \<netHttpBinding></span></span>

<span data-ttu-id="b4a27-103">HTTP 전송의 인증 매개 변수를 제어하는 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b4a27-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4a27-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4a27-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b4a27-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b4a27-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4a27-107">특성</span><span class="sxs-lookup"><span data-stu-id="b4a27-107">Attributes</span></span>  
  
|<span data-ttu-id="b4a27-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b4a27-108">Attribute</span></span>|<span data-ttu-id="b4a27-109">설명</span><span class="sxs-lookup"><span data-stu-id="b4a27-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4a27-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="b4a27-110">clientCredentialType</span></span>|<span data-ttu-id="b4a27-111">-HTTP 인증을 사용 하 여 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="b4a27-112">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-112">The default is `None`.</span></span> <span data-ttu-id="b4a27-113">이 특성은 <xref:System.ServiceModel.HttpClientCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="b4a27-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="b4a27-114">proxyCredentialType</span></span>|<span data-ttu-id="b4a27-115">-HTTP를 통해 프록시를 사용 하 여 도메인 내에서 클라이언트 인증을 수행할 때 사용할 자격 증명의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="b4a27-116">이 특성은 부모 `mode` 요소의 `security` 특성이 `Transport` 또는 `TransportCredentialsOnly`일 때만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="b4a27-117">이 특성은 <xref:System.ServiceModel.HttpProxyCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="b4a27-118">realm</span><span class="sxs-lookup"><span data-stu-id="b4a27-118">realm</span></span>|<span data-ttu-id="b4a27-119">다이제스트 또는 기본 인증의 HTTP 인증 체계에 사용되는 영역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="b4a27-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="b4a27-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="b4a27-121">policyEnforcement</span></span>|<span data-ttu-id="b4a27-122">이 열거형은 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="b4a27-123">1. Never – 정책이 적용 되지 않습니다 (확장 된 보호를 사용 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="b4a27-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="b4a27-124">2. 지원 됨 – 클라이언트에서 확장 된 보호를 지 원하는 경우에만 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="b4a27-125">3. 항상 – 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="b4a27-126">확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="b4a27-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="b4a27-127">protectionScenario</span></span>|<span data-ttu-id="b4a27-128">이 열거형은 정책을 통해 적용되는 보호 시나리오를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="b4a27-129">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="b4a27-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b4a27-130">Value</span><span class="sxs-lookup"><span data-stu-id="b4a27-130">Value</span></span>|<span data-ttu-id="b4a27-131">설명</span><span class="sxs-lookup"><span data-stu-id="b4a27-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b4a27-132">없음</span><span class="sxs-lookup"><span data-stu-id="b4a27-132">None</span></span>|<span data-ttu-id="b4a27-133">메시지가 전송 중에 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="b4a27-134">Basic</span><span class="sxs-lookup"><span data-stu-id="b4a27-134">Basic</span></span>|<span data-ttu-id="b4a27-135">기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="b4a27-136">다이제스트</span><span class="sxs-lookup"><span data-stu-id="b4a27-136">Digest</span></span>|<span data-ttu-id="b4a27-137">다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="b4a27-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b4a27-138">Ntlm</span></span>|<span data-ttu-id="b4a27-139">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="b4a27-140">Windows</span><span class="sxs-lookup"><span data-stu-id="b4a27-140">Windows</span></span>|<span data-ttu-id="b4a27-141">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="b4a27-142">proxyCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="b4a27-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b4a27-143">Value</span><span class="sxs-lookup"><span data-stu-id="b4a27-143">Value</span></span>|<span data-ttu-id="b4a27-144">설명</span><span class="sxs-lookup"><span data-stu-id="b4a27-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b4a27-145">없음</span><span class="sxs-lookup"><span data-stu-id="b4a27-145">None</span></span>|<span data-ttu-id="b4a27-146">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="b4a27-147">Basic</span><span class="sxs-lookup"><span data-stu-id="b4a27-147">Basic</span></span>|<span data-ttu-id="b4a27-148">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 기본 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="b4a27-149">다이제스트</span><span class="sxs-lookup"><span data-stu-id="b4a27-149">Digest</span></span>|<span data-ttu-id="b4a27-150">RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증에 정의된 대로 다이제스트 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="b4a27-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b4a27-151">Ntlm</span></span>|<span data-ttu-id="b4a27-152">Windows 인증이 실패할 경우 가능하면 NTLM 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="b4a27-153">Windows</span><span class="sxs-lookup"><span data-stu-id="b4a27-153">Windows</span></span>|<span data-ttu-id="b4a27-154">Windows 통합 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="b4a27-155">인증서</span><span class="sxs-lookup"><span data-stu-id="b4a27-155">Certificate</span></span>|<span data-ttu-id="b4a27-156">인증서를 사용하여 클라이언트 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="b4a27-157">이 옵션은 부모 `Mode` 요소의 `security` 특성이 Transport로 설정되어 있을 때만 작동하며 TransportCredentialOnly로 설정된 경우에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4a27-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b4a27-158">Child Elements</span></span>  

 <span data-ttu-id="b4a27-159">없음</span><span class="sxs-lookup"><span data-stu-id="b4a27-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4a27-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b4a27-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b4a27-161">요소</span><span class="sxs-lookup"><span data-stu-id="b4a27-161">Element</span></span>|<span data-ttu-id="b4a27-162">설명</span><span class="sxs-lookup"><span data-stu-id="b4a27-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="b4a27-163">의 보안 기능을 정의 합니다 [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="b4a27-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4a27-164">예제</span><span class="sxs-lookup"><span data-stu-id="b4a27-164">Example</span></span>  

 <span data-ttu-id="b4a27-165">다음 예제에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="b4a27-166">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a27-166">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b4a27-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4a27-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="b4a27-168">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b4a27-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b4a27-169">바인딩하</span><span class="sxs-lookup"><span data-stu-id="b4a27-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b4a27-170">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b4a27-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b4a27-171">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b4a27-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
