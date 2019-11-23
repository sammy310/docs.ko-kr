---
title: <idn> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698166"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="fd591-102">\<idn > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="fd591-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="fd591-103">IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[<span data-ttu-id="fd591-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="fd591-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fd591-105">&nbsp;&nbsp;[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fd591-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="fd591-106">&nbsp;&nbsp;&nbsp;&nbsp;**idn**\<</span><span class="sxs-lookup"><span data-stu-id="fd591-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd591-107">구문</span><span class="sxs-lookup"><span data-stu-id="fd591-107">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd591-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd591-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fd591-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd591-110">특성</span><span class="sxs-lookup"><span data-stu-id="fd591-110">Attributes</span></span>  

|<span data-ttu-id="fd591-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="fd591-111">**Element**</span></span>|<span data-ttu-id="fd591-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="fd591-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="fd591-113">IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다. 기본값은 none입니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="fd591-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd591-114">Child elements</span></span>

<span data-ttu-id="fd591-115">없음</span><span class="sxs-lookup"><span data-stu-id="fd591-115">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="fd591-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd591-116">Parent elements</span></span>

|<span data-ttu-id="fd591-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="fd591-117">**Element**</span></span>|<span data-ttu-id="fd591-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="fd591-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fd591-119">uri</span><span class="sxs-lookup"><span data-stu-id="fd591-119">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="fd591-120">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-120">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="fd591-121">주의</span><span class="sxs-lookup"><span data-stu-id="fd591-121">Remarks</span></span>

<span data-ttu-id="fd591-122">.NET Framework 3.5에서 기존 <xref:System.Uri> 클래스가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-122">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="fd591-123">3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-123">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="fd591-124">현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-124">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="fd591-125">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-125">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="fd591-126">Iri 지원을 사용 하는 다음 두 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-126">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="fd591-127">Machine.config 파일의 .NET Framework 2.0 디렉터리 아래에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-127">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="fd591-128">다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용할 것인지와 IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-128">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="fd591-129">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-129">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="fd591-130">세 가지 idn 관련 값을 사용 하는 DNS 서버에 따라 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-130">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="fd591-131">idn 사용 = All</span><span class="sxs-lookup"><span data-stu-id="fd591-131">idn enabled = All</span></span>  

     <span data-ttu-id="fd591-132">이 값은 punycode (IDN 이름)에 어떠한 유니코드 도메인 이름도 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-132">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="fd591-133">사용 하도록 설정 하는 idn AllExceptIntranet =</span><span class="sxs-lookup"><span data-stu-id="fd591-133">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="fd591-134">이 값은 Punycode 항목 (IDN 이름)을 사용 하려면 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-134">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="fd591-135">이 경우를 처리 하기 위해 로컬 인트라넷에 있는 국가별 이름을 인트라넷에 사용 되는 DNS 서버가 유니코드 이름 확인을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-135">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="fd591-136">idn 사용 = 없음</span><span class="sxs-lookup"><span data-stu-id="fd591-136">idn enabled = None</span></span>

     <span data-ttu-id="fd591-137">이 값은 Punycode를 사용 하도록 어떠한 유니코드 도메인 이름도 변환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-137">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="fd591-138">.NET Framework 2.0 동작과 일치 하는 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-138">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="fd591-139">IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-139">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="fd591-140">Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-140">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="fd591-141">대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-141">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="fd591-142">구성 파일</span><span class="sxs-lookup"><span data-stu-id="fd591-142">Configuration files</span></span>

<span data-ttu-id="fd591-143">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-143">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="fd591-144">예제</span><span class="sxs-lookup"><span data-stu-id="fd591-144">Example</span></span>

<span data-ttu-id="fd591-145">다음 예제에서는 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 <xref:System.Uri> 클래스에서 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd591-145">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fd591-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd591-146">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="fd591-147">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fd591-147">Network Settings Schema</span></span>](index.md)
