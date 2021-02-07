---
description: 다음에 대해 자세히 알아보세요. <metadata>
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 6cc1e472dbada72fe6a375a6832e7c9128dcda6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684427"
---
# \<metadata>

<span data-ttu-id="f1d16-102">서비스 메타데이터를 처리할 수 있는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-102">Specifies how service metadata can be processed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a><span data-ttu-id="f1d16-103">구문</span><span class="sxs-lookup"><span data-stu-id="f1d16-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1d16-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1d16-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f1d16-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1d16-106">특성</span><span class="sxs-lookup"><span data-stu-id="f1d16-106">Attributes</span></span>  

 <span data-ttu-id="f1d16-107">없음</span><span class="sxs-lookup"><span data-stu-id="f1d16-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1d16-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1d16-108">Child Elements</span></span>  
  
|<span data-ttu-id="f1d16-109">요소</span><span class="sxs-lookup"><span data-stu-id="f1d16-109">Element</span></span>|<span data-ttu-id="f1d16-110">설명</span><span class="sxs-lookup"><span data-stu-id="f1d16-110">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="f1d16-111">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-111">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="f1d16-112">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-112">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="f1d16-113">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-113">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="f1d16-114">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 엔드포인트 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-114">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="f1d16-115">가져오기 오류를 공개하는 속성 및 계약과 엔드포인트 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-115">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="f1d16-116">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-116">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1d16-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1d16-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f1d16-118">요소</span><span class="sxs-lookup"><span data-stu-id="f1d16-118">Element</span></span>|<span data-ttu-id="f1d16-119">설명</span><span class="sxs-lookup"><span data-stu-id="f1d16-119">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="f1d16-120">클라이언트 섹션은 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d16-120">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1d16-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1d16-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="f1d16-122">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f1d16-122">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="f1d16-123">클라이언트</span><span class="sxs-lookup"><span data-stu-id="f1d16-123">Clients</span></span>](../../../wcf/feature-details/clients.md)
