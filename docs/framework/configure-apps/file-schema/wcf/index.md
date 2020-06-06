---
title: WCF 구성 스키마
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 866b0639f4391e1898bbe36e458df87e3c24bfff
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77448661"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="cd258-102">WCF 구성 스키마</span><span class="sxs-lookup"><span data-stu-id="cd258-102">WCF Configuration Schema</span></span>
<span data-ttu-id="cd258-103">WCF (Windows Communication Foundation) 구성 요소를 사용 하 여 WCF 서비스와 클라이언트 응용 프로그램을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="cd258-104">[구성 편집기 도구(SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md)를 사용하여 클라이언트 및 서비스에 대한 구성 파일을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="cd258-105">구성 파일은 XML 형식이므로 텍스트 편집기를 사용하여 구성 파일을 수동으로 편집하려면 XML에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="cd258-106">그렇지 않으면 찾을 수 없는 XML 요소 태그나 특성과 같은 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="cd258-107">XML 요소 태그 및 속성이 대소문자를 구분하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="cd258-108">WCF 구성 시스템은 네임 스페이스를 기반으로 <xref:System.Configuration> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="cd258-109">따라서 애플리케이션 및 구성의 보안을 향상시키기 위해 구성 잠금, 암호화 및 병합과 같은 <xref:System.Configuration> 네임스페이스에서 제공하는 표준 기능을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="cd258-110">이러한 개념에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd258-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="cd258-111">[구성 정보 암호화](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd258-111">[Encrypting Configuration Information](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="cd258-112">[구성 설정 잠금](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd258-112">[Locking Configuration Settings](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="cd258-113">이 섹션에서는 각 구성 항목의 가능한 모든 값 및 이 값이 다른 WCF 구성 요소와 상호 작용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="cd258-114">다음 맵은 WCF 구성 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![WCF 구성 스키마를 보여 주는 다이어그램입니다.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="cd258-116">잠재적 보안 위협을 방지 하기 위해 적절 한 ACL (Access Control 목록)을 사용 하 여 응용 프로그램 구성 파일 (app.config)의 WCF 구성 섹션을 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="cd258-117">예를 들어, 적절한 사용자만이 애플리케이션 바인딩의 보안 설정 또는 서비스에 대한 구성 파일의 서비스 모델 섹션에 액세스하거나 이를 수정할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd258-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cd258-118">In This Section</span></span>  
 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="cd258-119">`ServiceModel` 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-119">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="cd258-120">SMSvcHost.exe 도구를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-120">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="cd258-121"><xref:System.Runtime.Serialization.DataContractSerializer>와 같은 serializer를 사용하는 경우 옵션 설정의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-121">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cd258-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="cd258-122">Related Sections</span></span>  
 [<span data-ttu-id="cd258-123">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="cd258-123">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="cd258-124">WCF 서비스 및 클라이언트를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd258-124">Describes how to configure WCF services and clients.</span></span>
