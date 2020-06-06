---
title: <iriParsing> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698098"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="f3caf-102">\<iriParsing> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="f3caf-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="f3caf-103">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="f3caf-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3caf-104">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3caf-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3caf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f3caf-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3caf-107">특성</span><span class="sxs-lookup"><span data-stu-id="f3caf-107">Attributes</span></span>  
  
|<span data-ttu-id="f3caf-108">**요소**</span><span class="sxs-lookup"><span data-stu-id="f3caf-108">**Element**</span></span>|<span data-ttu-id="f3caf-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="f3caf-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="f3caf-110">IRI 구문 분석이 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-110">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="f3caf-111">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3caf-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3caf-112">Child Elements</span></span>  
 <span data-ttu-id="f3caf-113">None</span><span class="sxs-lookup"><span data-stu-id="f3caf-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3caf-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3caf-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f3caf-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="f3caf-115">**Element**</span></span>|<span data-ttu-id="f3caf-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="f3caf-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f3caf-117">uri</span><span class="sxs-lookup"><span data-stu-id="f3caf-117">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="f3caf-118">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-118">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3caf-119">설명</span><span class="sxs-lookup"><span data-stu-id="f3caf-119">Remarks</span></span>  
 <span data-ttu-id="f3caf-120"><xref:System.Uri>.NET Framework 3.5에서 기존 클래스가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-120">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="f3caf-121">3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-121">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="f3caf-122">현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-122">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="f3caf-123">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-123">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="f3caf-124">IRI에 대 한 지원을 사용 하도록 설정 하려면 다음 두 가지 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-124">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="f3caf-125">Machine.config 파일의 .NET Framework 2.0 디렉터리 아래에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-125">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="f3caf-126">IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-126">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="f3caf-127">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-127">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="f3caf-128">IRI 구문 분석 (iriParsing 분석 사용 =)을 사용 하면 `true` RFC 3987의 최신 IRI 규칙에 따라 정규화 및 문자 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-128">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="f3caf-129">기본값은 이며 `false` rfc 2396 및 rfc 3986 (IPv6 리터럴의 경우)에 따라 정규화 및 문자 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-129">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="f3caf-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f3caf-130">Configuration Files</span></span>  
 <span data-ttu-id="f3caf-131">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3caf-132">예제</span><span class="sxs-lookup"><span data-stu-id="f3caf-132">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f3caf-133">Description</span><span class="sxs-lookup"><span data-stu-id="f3caf-133">Description</span></span>  
 <span data-ttu-id="f3caf-134">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3caf-134">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f3caf-135">코드</span><span class="sxs-lookup"><span data-stu-id="f3caf-135">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3caf-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3caf-136">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="f3caf-137">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f3caf-137">Network Settings Schema</span></span>](index.md)
