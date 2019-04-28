---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 0b06d61a33cd6a704a5ab0f75d29bde3f72d77fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788429"
---
# <a name="servicemetadata"></a><span data-ttu-id="9ca0d-101">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="9ca0d-101">\<serviceMetadata></span></span>
<span data-ttu-id="9ca0d-102">서비스 메타데이터 및 관련 정보의 게시를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-102">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="9ca0d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ca0d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9ca0d-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9ca0d-104">\<behaviors></span></span>  
<span data-ttu-id="9ca0d-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ca0d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9ca0d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9ca0d-106">\<behavior></span></span>  
<span data-ttu-id="9ca0d-107">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="9ca0d-107">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca0d-108">구문</span><span class="sxs-lookup"><span data-stu-id="9ca0d-108">Syntax</span></span>  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ca0d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ca0d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9ca0d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ca0d-111">특성</span><span class="sxs-lookup"><span data-stu-id="9ca0d-111">Attributes</span></span>  
  
|<span data-ttu-id="9ca0d-112">특성</span><span class="sxs-lookup"><span data-stu-id="9ca0d-112">Attribute</span></span>|<span data-ttu-id="9ca0d-113">설명</span><span class="sxs-lookup"><span data-stu-id="9ca0d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ca0d-114">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="9ca0d-114">externalMetadataLocation</span></span>|<span data-ttu-id="9ca0d-115">자동 생성된 WSDL 대신 WSDL 및 MEX 요청에 대한 응답으로 사용자에게 반환되는 WSDL 파일의 위치가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-115">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="9ca0d-116">이 특성을 설정하지 않으면 기본 WSDL이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-116">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="9ca0d-117">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-117">The default is an empty string.</span></span>|  
|<span data-ttu-id="9ca0d-118">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="9ca0d-118">httpGetBinding</span></span>|<span data-ttu-id="9ca0d-119">HTTP GET을 통해 메타데이터 검색에 사용할 바인딩 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-119">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="9ca0d-120">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-120">This setting is optional.</span></span> <span data-ttu-id="9ca0d-121">이 설정을 지정하지 않으면 기본 바인딩이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-121">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="9ca0d-122"><xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-122">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9ca0d-123">또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-123">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="9ca0d-124">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ca0d-124">httpGetBindingConfiguration</span></span>|<span data-ttu-id="9ca0d-125">이 바인딩의 추가 구성 정보를 참조하는 `httpGetBinding` 특성에 지정된 바인딩의 이름을 설정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-125">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="9ca0d-126">이와 동일한 이름이 `<bindings>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-126">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="9ca0d-127">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9ca0d-127">httpGetEnabled</span></span>|<span data-ttu-id="9ca0d-128">HTTP/Get 요청을 사용하여 검색을 위해 서비스 메타데이터를 게시하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-128">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="9ca0d-129">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-129">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9ca0d-130">httpGetUrl 특성이 지정되지 않을 경우 메타데이터가 게시되는 주소는 서비스 주소에 "?wsdl"을 붙인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-130">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="9ca0d-131">예를 들어, 서비스 주소가 "http://localhost:8080/CalculatorService", HTTP/Get 메타 데이터 주소는 "http://localhost:8080/CalculatorService?wsdl"입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-131">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="9ca0d-132">이 속성이 `false`, HTTP 또는 HTTPS, 서비스의 주소를 따르지 않습니다 또는 "? wsdl"이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-132">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="9ca0d-133">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="9ca0d-133">httpGetUrl</span></span>|<span data-ttu-id="9ca0d-134">HTTP/Get 요청을 사용하여 검색을 위해 메타데이터가 게시될 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-134">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="9ca0d-135">상대 URI가 지정되면 해당 URI는 서비스의 기본 주소에 상대적으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-135">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="9ca0d-136">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="9ca0d-136">httpsGetBinding</span></span>|<span data-ttu-id="9ca0d-137">HTTPS GET을 통해 메타데이터 검색에 사용할 바인딩 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-137">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="9ca0d-138">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-138">This setting is optional.</span></span> <span data-ttu-id="9ca0d-139">이 설정을 지정하지 않으면 기본 바인딩이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-139">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="9ca0d-140"><xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-140">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9ca0d-141">또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-141">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="9ca0d-142">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ca0d-142">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="9ca0d-143">이 바인딩의 추가 구성 정보를 참조하는 `httpsGetBinding` 특성에 지정된 바인딩의 이름을 설정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-143">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="9ca0d-144">이와 동일한 이름이 `<bindings>` 섹션에서 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-144">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="9ca0d-145">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9ca0d-145">httpsGetEnabled</span></span>|<span data-ttu-id="9ca0d-146">HTTPS/Get 요청을 사용하여 검색을 위해 서비스 메타데이터를 게시하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-146">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="9ca0d-147">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-147">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9ca0d-148">httpsGetUrl 특성이 지정되지 않을 경우 메타데이터가 게시되는 주소는 서비스 주소에 "?wsdl"를 붙인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-148">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="9ca0d-149">예를 들어, 서비스 주소가 "https://localhost:8080/CalculatorService", HTTP/Get 메타 데이터 주소는 "https://localhost:8080/CalculatorService?wsdl"입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-149">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="9ca0d-150">이 속성이 `false`, HTTP 또는 HTTPS, 서비스의 주소를 따르지 않습니다 또는 "? wsdl"이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-150">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="9ca0d-151">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="9ca0d-151">httpsGetUrl</span></span>|<span data-ttu-id="9ca0d-152">HTTPS/Get 요청을 사용하여 검색을 위해 메타데이터가 게시될 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-152">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="9ca0d-153">policyVersion</span><span class="sxs-lookup"><span data-stu-id="9ca0d-153">policyVersion</span></span>|<span data-ttu-id="9ca0d-154">사용 중인 WS-Policy 사양의 버전을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-154">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="9ca0d-155">이 특성은 <xref:System.ServiceModel.Description.PolicyVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-155">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ca0d-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ca0d-156">Child Elements</span></span>  
 <span data-ttu-id="9ca0d-157">없음</span><span class="sxs-lookup"><span data-stu-id="9ca0d-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ca0d-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ca0d-158">Parent Elements</span></span>  
  
|<span data-ttu-id="9ca0d-159">요소</span><span class="sxs-lookup"><span data-stu-id="9ca0d-159">Element</span></span>|<span data-ttu-id="9ca0d-160">설명</span><span class="sxs-lookup"><span data-stu-id="9ca0d-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ca0d-161">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9ca0d-161">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9ca0d-162">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-162">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca0d-163">설명</span><span class="sxs-lookup"><span data-stu-id="9ca0d-163">Remarks</span></span>  
 <span data-ttu-id="9ca0d-164">이 구성 요소를 사용하면 서비스의 메타데이터 게시 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-164">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="9ca0d-165">잠재적으로 중요 한 서비스 메타 데이터가 실수로 공개를 방지 하려면 Windows Communication Foundation (WCF) 서비스에 대 한 기본 구성 메타 데이터 게시를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-165">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="9ca0d-166">이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-166">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="9ca0d-167">이 구성 요소를 사용하면 서비스에 대해 이 게시 동작을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-167">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="9ca0d-168">이 동작을 구성 하는 자세한 예제를 보려면 [메타 데이터 게시 동작](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-168">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="9ca0d-169">선택적 `httpGetBinding` 및 `httpsGetBinding` 특성을 사용하면 HTTP GET 또는 HTTPS GET을 통해 메타데이터 검색에 사용되는 바인딩을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-169">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="9ca0d-170">바인딩을 지정하지 않으면 메타데이터 검색에 기본 바인딩(HTTP의 경우 `HttpTransportBindingElement`, HTTPS의 경우 `HttpsTransportBindingElement`)이 적절하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-170">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="9ca0d-171">기본 제공 WCF 바인딩에는 이러한 특성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-171">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="9ca0d-172"><xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-172">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="9ca0d-173">또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-173">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="9ca0d-174">악의적인 사용자에 대한 서비스 노출을 줄이기 위해 HTTPS(HTTP를 통한 SSL) 메커니즘을 사용하여 전송 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-174">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="9ca0d-175">이렇게 하려면 먼저 적절한 X.509 인증서를 서비스를 호스트하는 컴퓨터의 특정 포트에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-175">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="9ca0d-176">(자세한 내용은 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) 그런 다음 이 요소를 서비스 구성에 추가하고 `httpsGetEnabled` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-176">(For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="9ca0d-177">마지막으로 다음 예제와 같이 `httpsGetUrl` 특성을 서비스 메타데이터 엔드포인트의 URL로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-177">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a><span data-ttu-id="9ca0d-178">예제</span><span class="sxs-lookup"><span data-stu-id="9ca0d-178">Example</span></span>  
 <span data-ttu-id="9ca0d-179">다음 예제를 사용 하 여 메타 데이터를 노출 하도록 서비스를 구성 합니다 \<serviceMetadata > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-179">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="9ca0d-180">또한 `IMetadataExchange` 계약을 WS-MetadataExchange(MEX) 프로토콜의 구현으로 노출하도록 엔드포인트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-180">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="9ca0d-181">예제에서는 `mexHttpBinding`에 해당하는 편의 표준 바인딩인 `wsHttpBinding`을 `None`으로 설정된 보안 모드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-181">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="9ca0d-182">"Mex"의 상대 주소는 끝점에는 확인 하는 경우 서비스의 기본 주소의 끝점 주소에서 결과 `http://localhost/servicemodelsamples/service.svc/mex`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca0d-182">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="9ca0d-183">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ca0d-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="9ca0d-184">보안 동작</span><span class="sxs-lookup"><span data-stu-id="9ca0d-184">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9ca0d-185">메타데이터 게시 동작</span><span class="sxs-lookup"><span data-stu-id="9ca0d-185">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
