---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854764"
---
# \<wsdlImporter>
<span data-ttu-id="113b7-101">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="113b7-102">구문</span><span class="sxs-lookup"><span data-stu-id="113b7-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="113b7-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="113b7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="113b7-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="113b7-105">특성</span><span class="sxs-lookup"><span data-stu-id="113b7-105">Attributes</span></span>  
  
|<span data-ttu-id="113b7-106">attribute</span><span class="sxs-lookup"><span data-stu-id="113b7-106">Attribute</span></span>|<span data-ttu-id="113b7-107">Description</span><span class="sxs-lookup"><span data-stu-id="113b7-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="113b7-108">이 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="113b7-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="113b7-109">Child Elements</span></span>  
 <span data-ttu-id="113b7-110">없음</span><span class="sxs-lookup"><span data-stu-id="113b7-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="113b7-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="113b7-111">Parent Elements</span></span>  
  
|<span data-ttu-id="113b7-112">요소</span><span class="sxs-lookup"><span data-stu-id="113b7-112">Element</span></span>|<span data-ttu-id="113b7-113">Description</span><span class="sxs-lookup"><span data-stu-id="113b7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="113b7-114">WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="113b7-115">설명</span><span class="sxs-lookup"><span data-stu-id="113b7-115">Remarks</span></span>  
 <span data-ttu-id="113b7-116">WSDL 가져오기는 메타데이터를 가져오고 그 정보를 계약 및 엔드포인트 정보를 나타내는 다양한 클래스로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="113b7-117">가져오기 오류를 공개하는 속성 및 계약과 엔드포인트 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="113b7-118">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="113b7-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113b7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="113b7-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="113b7-120">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="113b7-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="113b7-121">클라이언트</span><span class="sxs-lookup"><span data-stu-id="113b7-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
