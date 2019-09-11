---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854764"
---
# <a name="wsdlimporter"></a><span data-ttu-id="6952c-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="6952c-101">\<wsdlImporter></span></span>
<span data-ttu-id="6952c-102">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="6952c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6952c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6952c-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6952c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6952c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<클라이언트 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="6952c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="6952c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<메타 데이터 >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6952c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="6952c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsdlImporters >** ](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="6952c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="6952c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsdlImporter >**</span><span class="sxs-lookup"><span data-stu-id="6952c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6952c-109">구문</span><span class="sxs-lookup"><span data-stu-id="6952c-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6952c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6952c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6952c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6952c-112">특성</span><span class="sxs-lookup"><span data-stu-id="6952c-112">Attributes</span></span>  
  
|<span data-ttu-id="6952c-113">특성</span><span class="sxs-lookup"><span data-stu-id="6952c-113">Attribute</span></span>|<span data-ttu-id="6952c-114">설명</span><span class="sxs-lookup"><span data-stu-id="6952c-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6952c-115">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6952c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6952c-116">Child Elements</span></span>  
 <span data-ttu-id="6952c-117">없음</span><span class="sxs-lookup"><span data-stu-id="6952c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6952c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6952c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6952c-119">요소</span><span class="sxs-lookup"><span data-stu-id="6952c-119">Element</span></span>|<span data-ttu-id="6952c-120">설명</span><span class="sxs-lookup"><span data-stu-id="6952c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6952c-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="6952c-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="6952c-122">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6952c-123">설명</span><span class="sxs-lookup"><span data-stu-id="6952c-123">Remarks</span></span>  
 <span data-ttu-id="6952c-124">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 엔드포인트 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="6952c-125">가져오기 오류를 공개하는 속성 및 계약과 엔드포인트 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="6952c-126">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6952c-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6952c-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="6952c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="6952c-128">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="6952c-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="6952c-129">클라이언트</span><span class="sxs-lookup"><span data-stu-id="6952c-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
