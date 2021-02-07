---
description: '다음에 대 한 자세한 정보: <iriParsing> 요소 (Uri 설정)'
title: <iriParsing> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 460216b64056cd9c9f769c5bcd1b651d249e98b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740303"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="a91c4-103">\<iriParsing> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="a91c4-103">\<iriParsing> Element (Uri Settings)</span></span>

<span data-ttu-id="a91c4-104">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-104">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="a91c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="a91c4-105">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a91c4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a91c4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a91c4-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a91c4-108">특성</span><span class="sxs-lookup"><span data-stu-id="a91c4-108">Attributes</span></span>  
  
|<span data-ttu-id="a91c4-109">**요소**</span><span class="sxs-lookup"><span data-stu-id="a91c4-109">**Element**</span></span>|<span data-ttu-id="a91c4-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="a91c4-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="a91c4-111">IRI 구문 분석이 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-111">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="a91c4-112">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-112">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a91c4-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a91c4-113">Child Elements</span></span>  

 <span data-ttu-id="a91c4-114">없음</span><span class="sxs-lookup"><span data-stu-id="a91c4-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a91c4-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a91c4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a91c4-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="a91c4-116">**Element**</span></span>|<span data-ttu-id="a91c4-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="a91c4-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a91c4-118">uri</span><span class="sxs-lookup"><span data-stu-id="a91c4-118">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="a91c4-119">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-119">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a91c4-120">설명</span><span class="sxs-lookup"><span data-stu-id="a91c4-120">Remarks</span></span>  

 <span data-ttu-id="a91c4-121"><xref:System.Uri>.NET Framework 3.5에서 기존 클래스가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-121">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="a91c4-122">3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-122">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="a91c4-123">현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-123">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="a91c4-124">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-124">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a91c4-125">IRI에 대 한 지원을 사용 하도록 설정 하려면 다음 두 가지 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-125">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="a91c4-126">.NET Framework 2.0 디렉터리 아래의 machine.config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-126">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="a91c4-127">IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-127">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="a91c4-128">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-128">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="a91c4-129">IRI 구문 분석 (iriParsing 분석 사용 =)을 사용 하면 `true` RFC 3987의 최신 IRI 규칙에 따라 정규화 및 문자 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-129">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="a91c4-130">기본값은 이며 `false` rfc 2396 및 rfc 3986 (IPv6 리터럴의 경우)에 따라 정규화 및 문자 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-130">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="a91c4-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a91c4-131">Configuration Files</span></span>  

 <span data-ttu-id="a91c4-132">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a91c4-133">예제</span><span class="sxs-lookup"><span data-stu-id="a91c4-133">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a91c4-134">설명</span><span class="sxs-lookup"><span data-stu-id="a91c4-134">Description</span></span>  

 <span data-ttu-id="a91c4-135">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a91c4-135">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a91c4-136">코드</span><span class="sxs-lookup"><span data-stu-id="a91c4-136">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a91c4-137">참조</span><span class="sxs-lookup"><span data-stu-id="a91c4-137">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="a91c4-138">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a91c4-138">Network Settings Schema</span></span>](index.md)
