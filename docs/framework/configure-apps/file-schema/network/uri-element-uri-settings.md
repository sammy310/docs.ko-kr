---
title: <uri> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697433"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="0ebf8-102">\<uri> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="0ebf8-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="0ebf8-103">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="0ebf8-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ebf8-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ebf8-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0ebf8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0ebf8-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ebf8-107">특성</span><span class="sxs-lookup"><span data-stu-id="0ebf8-107">Attributes</span></span>  
 <span data-ttu-id="0ebf8-108">없음</span><span class="sxs-lookup"><span data-stu-id="0ebf8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ebf8-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0ebf8-109">Child Elements</span></span>  
  
|<span data-ttu-id="0ebf8-110">**요소**</span><span class="sxs-lookup"><span data-stu-id="0ebf8-110">**Element**</span></span>|<span data-ttu-id="0ebf8-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="0ebf8-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0ebf8-112">idn</span><span class="sxs-lookup"><span data-stu-id="0ebf8-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="0ebf8-113">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="0ebf8-114">Iriparsing></span><span class="sxs-lookup"><span data-stu-id="0ebf8-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="0ebf8-115">IRI (국가별 리소스 식별자) 구문 분석이에 적용 되는지 <xref:System.Uri> 여부와 iri 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="0ebf8-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="0ebf8-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="0ebf8-117">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ebf8-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0ebf8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0ebf8-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="0ebf8-119">**Element**</span></span>|<span data-ttu-id="0ebf8-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="0ebf8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0ebf8-121">구성</span><span class="sxs-lookup"><span data-stu-id="0ebf8-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="0ebf8-122">모든 네임 스페이스에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebf8-123">설명</span><span class="sxs-lookup"><span data-stu-id="0ebf8-123">Remarks</span></span>  
 <span data-ttu-id="0ebf8-124">`uri`요소는 <xref:System.Uri> 네임 스페이스의 클래스에서 사용 하는 클래스의 멤버에 대 한 설정을 포함 합니다 <xref:System.Net> .</span><span class="sxs-lookup"><span data-stu-id="0ebf8-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="0ebf8-125">설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ebf8-126">예제</span><span class="sxs-lookup"><span data-stu-id="0ebf8-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0ebf8-127">Description</span><span class="sxs-lookup"><span data-stu-id="0ebf8-127">Description</span></span>  
 <span data-ttu-id="0ebf8-128">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="0ebf8-129">또한이 예제에서는 모든 구성표 설정을 지운 다음 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않는 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebf8-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0ebf8-130">코드</span><span class="sxs-lookup"><span data-stu-id="0ebf8-130">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ebf8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ebf8-131">See also</span></span>

- [<span data-ttu-id="0ebf8-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0ebf8-132">Network Settings Schema</span></span>](index.md)
