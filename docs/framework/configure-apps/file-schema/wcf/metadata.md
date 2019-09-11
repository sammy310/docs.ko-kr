---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855234"
---
# <a name="metadata"></a><span data-ttu-id="eaaa3-101">\<metadata></span><span class="sxs-lookup"><span data-stu-id="eaaa3-101">\<metadata></span></span>
<span data-ttu-id="eaaa3-102">서비스 메타데이터를 처리할 수 있는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="eaaa3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaaa3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eaaa3-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eaaa3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eaaa3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="eaaa3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="eaaa3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<메타 데이터 >**</span><span class="sxs-lookup"><span data-stu-id="eaaa3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaaa3-107">구문</span><span class="sxs-lookup"><span data-stu-id="eaaa3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaaa3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eaaa3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eaaa3-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaaa3-110">특성</span><span class="sxs-lookup"><span data-stu-id="eaaa3-110">Attributes</span></span>  
 <span data-ttu-id="eaaa3-111">없음</span><span class="sxs-lookup"><span data-stu-id="eaaa3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eaaa3-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eaaa3-112">Child Elements</span></span>  
  
|<span data-ttu-id="eaaa3-113">요소</span><span class="sxs-lookup"><span data-stu-id="eaaa3-113">Element</span></span>|<span data-ttu-id="eaaa3-114">Description</span><span class="sxs-lookup"><span data-stu-id="eaaa3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaaa3-115">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="eaaa3-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="eaaa3-116">바인딩에 대한 사용자 지정 정책 어설션의 가져오기를 제어하는 모든 정책 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="eaaa3-117">정책 가져오기는, 바인딩 기능에 대한 사용자 지정 정책 어설션을 검색하거나 어설션에서 요구하는 기능을 구현하는 사용자 지정 바인딩 요소를 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="eaaa3-118">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="eaaa3-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="eaaa3-119">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="eaaa3-120">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 엔드포인트 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="eaaa3-121">가져오기 오류를 공개하는 속성 및 계약과 엔드포인트 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="eaaa3-122">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eaaa3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eaaa3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eaaa3-124">요소</span><span class="sxs-lookup"><span data-stu-id="eaaa3-124">Element</span></span>|<span data-ttu-id="eaaa3-125">Description</span><span class="sxs-lookup"><span data-stu-id="eaaa3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaaa3-126">\<client></span><span class="sxs-lookup"><span data-stu-id="eaaa3-126">\<client></span></span>](client.md)|<span data-ttu-id="eaaa3-127">클라이언트 섹션은 클라이언트가 연결할 수 있는 엔드포인트 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa3-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eaaa3-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="eaaa3-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="eaaa3-129">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="eaaa3-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="eaaa3-130">클라이언트</span><span class="sxs-lookup"><span data-stu-id="eaaa3-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
