---
title: <Uri> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663973"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="07390-102">\<Uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="07390-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="07390-103">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="07390-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="07390-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="07390-105">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="07390-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="07390-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="07390-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="07390-107">구문</span><span class="sxs-lookup"><span data-stu-id="07390-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07390-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="07390-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07390-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07390-110">특성</span><span class="sxs-lookup"><span data-stu-id="07390-110">Attributes</span></span>  
 <span data-ttu-id="07390-111">없음</span><span class="sxs-lookup"><span data-stu-id="07390-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07390-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="07390-112">Child Elements</span></span>  
  
|<span data-ttu-id="07390-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="07390-113">**Element**</span></span>|<span data-ttu-id="07390-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="07390-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="07390-115">idn</span><span class="sxs-lookup"><span data-stu-id="07390-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="07390-116">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="07390-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="07390-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="07390-118">Iri (국가별 리소스 식별자) 구문 분석이에 <xref:System.Uri> 적용 되는지 여부와 iri 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="07390-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="07390-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="07390-120">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07390-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="07390-121">Parent Elements</span></span>  
  
|<span data-ttu-id="07390-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="07390-122">**Element**</span></span>|<span data-ttu-id="07390-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="07390-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="07390-124">configuration</span><span class="sxs-lookup"><span data-stu-id="07390-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="07390-125">모든 네임 스페이스에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07390-126">설명</span><span class="sxs-lookup"><span data-stu-id="07390-126">Remarks</span></span>  
 <span data-ttu-id="07390-127">요소 `uri` 는 <xref:System.Net> 네임 스페이스의 클래스에서 사용 <xref:System.Uri> 하는 클래스의 멤버에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="07390-128">설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07390-129">예제</span><span class="sxs-lookup"><span data-stu-id="07390-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="07390-130">설명</span><span class="sxs-lookup"><span data-stu-id="07390-130">Description</span></span>  
 <span data-ttu-id="07390-131">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07390-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="07390-132">또한이 예제에서는 모든 구성표 설정을 지운 다음 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않는 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07390-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="07390-133">코드</span><span class="sxs-lookup"><span data-stu-id="07390-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07390-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="07390-134">See also</span></span>

- [<span data-ttu-id="07390-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="07390-135">Network Settings Schema</span></span>](index.md)
