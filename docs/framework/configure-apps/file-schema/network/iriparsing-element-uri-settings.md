---
title: <iriParsing> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664082"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="984c1-102">\<iriParsing 분석 > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="984c1-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="984c1-103">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="984c1-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="984c1-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="984c1-105">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="984c1-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="984c1-106">\<Uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="984c1-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="984c1-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="984c1-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="984c1-108">구문</span><span class="sxs-lookup"><span data-stu-id="984c1-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="984c1-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="984c1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="984c1-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="984c1-111">특성</span><span class="sxs-lookup"><span data-stu-id="984c1-111">Attributes</span></span>  
  
|<span data-ttu-id="984c1-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="984c1-112">**Element**</span></span>|<span data-ttu-id="984c1-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="984c1-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="984c1-114">IRI 구문 분석이 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="984c1-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="984c1-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="984c1-116">Child Elements</span></span>  
 <span data-ttu-id="984c1-117">없음</span><span class="sxs-lookup"><span data-stu-id="984c1-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="984c1-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="984c1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="984c1-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="984c1-119">**Element**</span></span>|<span data-ttu-id="984c1-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="984c1-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="984c1-121">uri</span><span class="sxs-lookup"><span data-stu-id="984c1-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="984c1-122">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="984c1-123">설명</span><span class="sxs-lookup"><span data-stu-id="984c1-123">Remarks</span></span>  
 <span data-ttu-id="984c1-124">.NET Framework 3.5 <xref:System.Uri> 에서 기존 클래스가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="984c1-125">3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="984c1-126">현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="984c1-127">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="984c1-128">Iri 지원을 사용 하는 다음 두 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="984c1-129">Machine.config 파일의 .NET Framework 2.0 디렉터리 아래에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="984c1-130">IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="984c1-131">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="984c1-132">IRI 구분 분석 (iriParsing 사용 = `true`) 문자 검사가 최신 IRI 규칙 RFC 3987 및 정규화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="984c1-133">기본값 `false` 은 이며 rfc 2396 및 rfc 3986 (IPv6 리터럴의 경우)에 따라 정규화 및 문자 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="984c1-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="984c1-134">Configuration Files</span></span>  
 <span data-ttu-id="984c1-135">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="984c1-136">예제</span><span class="sxs-lookup"><span data-stu-id="984c1-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="984c1-137">설명</span><span class="sxs-lookup"><span data-stu-id="984c1-137">Description</span></span>  
 <span data-ttu-id="984c1-138">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="984c1-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="984c1-139">코드</span><span class="sxs-lookup"><span data-stu-id="984c1-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="984c1-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="984c1-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="984c1-141">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="984c1-141">Network Settings Schema</span></span>](index.md)
