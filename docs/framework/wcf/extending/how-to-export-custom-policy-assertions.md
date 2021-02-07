---
description: '자세히 알아보기: 방법: 사용자 지정 정책 어설션 내보내기'
title: '방법: 사용자 지정 정책 어설션 내보내기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
ms.openlocfilehash: b49d5a88809039f59537d79f92e31711085e580a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668932"
---
# <a name="how-to-export-custom-policy-assertions"></a><span data-ttu-id="503f6-103">방법: 사용자 지정 정책 어설션 내보내기</span><span class="sxs-lookup"><span data-stu-id="503f6-103">How to: Export Custom Policy Assertions</span></span>

<span data-ttu-id="503f6-104">정책 어설션은 서비스 엔드포인트의 기능 및 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-104">Policy assertions describe the capabilities and requirements of a service endpoint.</span></span> <span data-ttu-id="503f6-105">서비스 애플리케이션은 서비스 메타데이터에서 사용자 지정 정책 어설션을 사용하여 엔드포인트, 바인딩 또는 계약 사용자 지정 정보에 대해 클라이언트 애플리케이션과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-105">Service applications can use custom policy assertions in service metadata to communicate endpoint, binding or contract customization information to the client application.</span></span> <span data-ttu-id="503f6-106">WCF (Windows Communication Foundation)를 사용 하 여 통신 하는 기능 또는 요구 사항에 따라 끝점, 작업 또는 메시지 주제의 WSDL 바인딩에 연결 된 정책 식에서 어설션을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-106">You can use Windows Communication Foundation (WCF) to export assertions in policy expressions attached in WSDL bindings at the endpoint, operation, or message subjects, depending upon the capabilities or requirements you are communicating.</span></span>  
  
 <span data-ttu-id="503f6-107">사용자 지정 정책 어설션은 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>의 <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> 인터페이스를 구현하고, 바인딩 요소를 서비스 엔드포인트의 바인딩에 직접 삽입하거나 바인딩 요소를 애플리케이션 구성 파일에 등록하여 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-107">Custom policy assertions are exported by implementing the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface on a <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> and either inserting the binding element directly into the binding of the service endpoint or by registering the binding element in your application configuration file.</span></span> <span data-ttu-id="503f6-108">정책 내보내기 구현을 통해 사용자 지정 정책 어설션을 <xref:System.Xml.XmlElement?displayProperty=nameWithType> 인스턴스로서 <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> 메서드에 전달된 <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType>의 해당 <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-108">Your policy export implementation should add your custom policy assertion as a <xref:System.Xml.XmlElement?displayProperty=nameWithType> instance to the appropriate <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> on the <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> passed into the <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> method.</span></span>  
  
 <span data-ttu-id="503f6-109">또한 <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 클래스의 <xref:System.ServiceModel.Description.WsdlExporter> 속성을 확인하고, 지정된 정책 버전에 따라 올바른 네임스페이스의 중첩된 정책 식 및 정책 프레임워크 특성을 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-109">In addition you must check the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property of the <xref:System.ServiceModel.Description.WsdlExporter> class and export nested policy expressions and policy framework attributes in the correct namespace based on the policy version specified.</span></span>  
  
 <span data-ttu-id="503f6-110">사용자 지정 정책 어설션을 가져오려면 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 및 [방법: 사용자 지정 정책 어설션 가져오기](how-to-import-custom-policy-assertions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="503f6-110">To import custom policy assertions, see <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> and [How to: Import Custom Policy Assertions](how-to-import-custom-policy-assertions.md).</span></span>  
  
### <a name="to-export-custom-policy-assertions"></a><span data-ttu-id="503f6-111">사용자 지정 정책 어설션을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="503f6-111">To export custom policy assertions</span></span>  
  
1. <span data-ttu-id="503f6-112"><xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>의 <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-112">Implement the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface on a <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>.</span></span> <span data-ttu-id="503f6-113">다음 코드 예제에서는 바인딩 수준에서 사용자 지정 정책 어설션의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-113">The following code example shows the implementation of a custom policy assertion at the binding level.</span></span>  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2. <span data-ttu-id="503f6-114">바인딩 요소를 엔드포인트 바인딩에 프로그래밍 방식으로 삽입하거나 애플리케이션 구성 파일을 사용하여 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-114">Insert the binding element into the endpoint binding either programmatically or using an application configuration file.</span></span> <span data-ttu-id="503f6-115">다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="503f6-115">See the following procedures.</span></span>  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a><span data-ttu-id="503f6-116">애플리케이션 구성 파일을 사용하여 바인딩 요소를 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="503f6-116">To insert a binding element using an application configuration file</span></span>  
  
1. <span data-ttu-id="503f6-117">사용자 지정 정책 어설션 바인딩 요소에 대한 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-117">Implement <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> for your custom policy assertion binding element.</span></span>  
  
2. <span data-ttu-id="503f6-118">요소를 사용 하 여 구성 파일에 바인딩 요소 확장을 추가 합니다 [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) .</span><span class="sxs-lookup"><span data-stu-id="503f6-118">Add the binding element extension to the configuration file using the [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) element.</span></span>  
  
3. <span data-ttu-id="503f6-119"><xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>을 사용하여 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-119">Build a custom binding using the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-insert-a-binding-element-programmatically"></a><span data-ttu-id="503f6-120">바인딩 요소를 프로그래밍 방식으로 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="503f6-120">To insert a binding element programmatically</span></span>  
  
1. <span data-ttu-id="503f6-121">새 <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>를 만들어 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-121">Create a new <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> and add it to a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span></span>  
  
2. <span data-ttu-id="503f6-122">1단계의 사용자 지정 바인딩을</span><span class="sxs-lookup"><span data-stu-id="503f6-122">Add the custom binding from step 1.</span></span> <span data-ttu-id="503f6-123">새 엔드포인트에 추가하고, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 메서드를 호출하여 해당 새 서비스 엔드포인트를 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-123">to a new endpoint and add that new service endpoint to the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> by calling the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
3. <span data-ttu-id="503f6-124"><xref:System.ServiceModel.ServiceHost> 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-124">Open the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="503f6-125">다음 코드 예제에서는 사용자 지정 바인딩을 만들고 프로그래밍 방식으로 바인딩 요소를 삽입하는 방법에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="503f6-125">The following code example shows the creation of a custom binding and the programmatic insertion of binding elements.</span></span>  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="503f6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="503f6-126">See also</span></span>

- <xref:System.ServiceModel.Description.IPolicyImportExtension>
- <xref:System.ServiceModel.Description.IPolicyExportExtension>
- [<span data-ttu-id="503f6-127">방법: 사용자 지정 정책 어설션 가져오기</span><span class="sxs-lookup"><span data-stu-id="503f6-127">How to: Import Custom Policy Assertions</span></span>](how-to-import-custom-policy-assertions.md)
