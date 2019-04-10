---
title: <Uri> 요소 (Uri 설정)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 1f3573babd2e363a78f0ad454f0ba36c87ba6390
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212144"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="160bf-102">\<Uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="160bf-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="160bf-103">.NET Framework uniform resource identifier (Uri)를 사용 하 여 표현 하는 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="160bf-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="160bf-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="160bf-105">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="160bf-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="160bf-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="160bf-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="160bf-107">구문</span><span class="sxs-lookup"><span data-stu-id="160bf-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="160bf-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="160bf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="160bf-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="160bf-110">특성</span><span class="sxs-lookup"><span data-stu-id="160bf-110">Attributes</span></span>  
 <span data-ttu-id="160bf-111">없음</span><span class="sxs-lookup"><span data-stu-id="160bf-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="160bf-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="160bf-112">Child Elements</span></span>  
  
|**<span data-ttu-id="160bf-113">요소</span><span class="sxs-lookup"><span data-stu-id="160bf-113">Element</span></span>**|**<span data-ttu-id="160bf-114">설명</span><span class="sxs-lookup"><span data-stu-id="160bf-114">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="160bf-115">idn</span><span class="sxs-lookup"><span data-stu-id="160bf-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="160bf-116">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="160bf-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="160bf-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="160bf-118">식별자 IRI (International Resource) 구문 분석에 적용 됩니다 지정 <xref:System.Uri> IRI 구문 분석 규칙을 적용 해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="160bf-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="160bf-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="160bf-120">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="160bf-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="160bf-121">Parent Elements</span></span>  
  
|**<span data-ttu-id="160bf-122">요소</span><span class="sxs-lookup"><span data-stu-id="160bf-122">Element</span></span>**|**<span data-ttu-id="160bf-123">설명</span><span class="sxs-lookup"><span data-stu-id="160bf-123">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="160bf-124">구성</span><span class="sxs-lookup"><span data-stu-id="160bf-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="160bf-125">모든 네임 스페이스에 대 한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="160bf-126">설명</span><span class="sxs-lookup"><span data-stu-id="160bf-126">Remarks</span></span>  
 <span data-ttu-id="160bf-127">`uri` 요소 멤버에 대 한 설정을 포함 합니다 <xref:System.Uri> 클래스에 의해 사용 되는 클래스는 <xref:System.Net> 네임 스페이스.</span><span class="sxs-lookup"><span data-stu-id="160bf-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="160bf-128">이 설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="160bf-129">예제</span><span class="sxs-lookup"><span data-stu-id="160bf-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="160bf-130">설명</span><span class="sxs-lookup"><span data-stu-id="160bf-130">Description</span></span>  
 <span data-ttu-id="160bf-131">다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> IRI 구문 분석 및 IDN 이름이 지원 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="160bf-132">이 예제에서는 모든 스키마 설정을 지웁니다 및 http 체계에 대 한 백분율로 인코딩된 경로 구분 기호를 이스케이프 하지 않아도 되도록 하는 것에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="160bf-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="160bf-133">코드</span><span class="sxs-lookup"><span data-stu-id="160bf-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="160bf-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="160bf-134">See also</span></span>

- [<span data-ttu-id="160bf-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="160bf-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
