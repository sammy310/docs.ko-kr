---
title: <uri> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697433"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="f90b7-102">\<uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="f90b7-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="f90b7-103">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="f90b7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f90b7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f90b7-105">&nbsp; @ no__t **\<uri >**</span><span class="sxs-lookup"><span data-stu-id="f90b7-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90b7-106">구문</span><span class="sxs-lookup"><span data-stu-id="f90b7-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f90b7-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f90b7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f90b7-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f90b7-109">특성</span><span class="sxs-lookup"><span data-stu-id="f90b7-109">Attributes</span></span>  
 <span data-ttu-id="f90b7-110">없음</span><span class="sxs-lookup"><span data-stu-id="f90b7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f90b7-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f90b7-111">Child Elements</span></span>  
  
|<span data-ttu-id="f90b7-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="f90b7-112">**Element**</span></span>|<span data-ttu-id="f90b7-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="f90b7-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f90b7-114">idn</span><span class="sxs-lookup"><span data-stu-id="f90b7-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="f90b7-115">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="f90b7-116">iriParsing</span><span class="sxs-lookup"><span data-stu-id="f90b7-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="f90b7-117">IRI (국가별 리소스 식별자) 구문 분석이 <xref:System.Uri>에 적용 되는지 여부와 IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="f90b7-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="f90b7-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="f90b7-119">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f90b7-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f90b7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f90b7-121">**요소**</span><span class="sxs-lookup"><span data-stu-id="f90b7-121">**Element**</span></span>|<span data-ttu-id="f90b7-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="f90b7-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f90b7-123">configuration</span><span class="sxs-lookup"><span data-stu-id="f90b7-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="f90b7-124">모든 네임 스페이스에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f90b7-125">설명</span><span class="sxs-lookup"><span data-stu-id="f90b7-125">Remarks</span></span>  
 <span data-ttu-id="f90b7-126">@No__t-0 요소는 <xref:System.Net> 네임 스페이스의 클래스에서 사용 하는 @no__t 1 클래스의 멤버에 대 한 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="f90b7-127">설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90b7-128">예제</span><span class="sxs-lookup"><span data-stu-id="f90b7-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f90b7-129">설명</span><span class="sxs-lookup"><span data-stu-id="f90b7-129">Description</span></span>  
 <span data-ttu-id="f90b7-130">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="f90b7-131">또한이 예제에서는 모든 구성표 설정을 지운 다음 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않는 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f90b7-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f90b7-132">코드</span><span class="sxs-lookup"><span data-stu-id="f90b7-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f90b7-133">참조</span><span class="sxs-lookup"><span data-stu-id="f90b7-133">See also</span></span>

- [<span data-ttu-id="f90b7-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f90b7-134">Network Settings Schema</span></span>](index.md)
