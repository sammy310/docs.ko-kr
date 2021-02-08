---
description: '다음에 대 한 자세한 정보: <idn> 요소 (Uri 설정)'
title: <idn> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: a53afd59b713a804d5b969521f468000dbbad6e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802478"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="810d4-103">\<idn> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="810d4-103">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="810d4-104">IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-104">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
## <a name="syntax"></a><span data-ttu-id="810d4-105">구문</span><span class="sxs-lookup"><span data-stu-id="810d4-105">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="810d4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="810d4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="810d4-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="810d4-108">특성</span><span class="sxs-lookup"><span data-stu-id="810d4-108">Attributes</span></span>  

|<span data-ttu-id="810d4-109">**요소**</span><span class="sxs-lookup"><span data-stu-id="810d4-109">**Element**</span></span>|<span data-ttu-id="810d4-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="810d4-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="810d4-111">IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다. 기본값은 none입니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-111">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="810d4-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="810d4-112">Child elements</span></span>

<span data-ttu-id="810d4-113">없음</span><span class="sxs-lookup"><span data-stu-id="810d4-113">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="810d4-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="810d4-114">Parent elements</span></span>

|<span data-ttu-id="810d4-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="810d4-115">**Element**</span></span>|<span data-ttu-id="810d4-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="810d4-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="810d4-117">uri</span><span class="sxs-lookup"><span data-stu-id="810d4-117">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="810d4-118">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-118">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="810d4-119">설명</span><span class="sxs-lookup"><span data-stu-id="810d4-119">Remarks</span></span>

<span data-ttu-id="810d4-120"><xref:System.Uri>.NET Framework 3.5에서 기존 클래스가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-120">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="810d4-121">3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-121">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="810d4-122">현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-122">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="810d4-123">이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-123">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="810d4-124">IRI에 대 한 지원을 사용 하도록 설정 하려면 다음 두 가지 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-124">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="810d4-125">machine.config 파일의 .NET Framework 2.0 디렉터리 아래에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-125">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="810d4-126">IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되도록 할지 여부와 IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-126">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="810d4-127">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-127">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="810d4-128">사용 되는 DNS 서버에 따라 IDN에 대해 다음과 같은 세 가지 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-128">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="810d4-129">idn 사용 = 모두</span><span class="sxs-lookup"><span data-stu-id="810d4-129">idn enabled = All</span></span>  

     <span data-ttu-id="810d4-130">이 값은 모든 유니코드 도메인 이름을 해당하는 Punycode 항목(IDN 이름)으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-130">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="810d4-131">idn 사용 = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="810d4-131">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="810d4-132">이 값은 해당 하는 Punycode (IDN 이름)를 사용 하도록 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-132">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="810d4-133">이 경우 로컬 인트라넷에서 국제 이름을 처리 하려면 인트라넷에 사용 되는 DNS 서버가 유니코드 이름 확인을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-133">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="810d4-134">idn 사용 = 없음</span><span class="sxs-lookup"><span data-stu-id="810d4-134">idn enabled = None</span></span>

     <span data-ttu-id="810d4-135">이 값은 Punycode를 사용하도록 어떠한 유니코드 도메인 이름도 변환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-135">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="810d4-136">이 값은 .NET Framework 2.0 동작과 일치하는 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-136">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="810d4-137">IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-137">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="810d4-138">Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-138">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="810d4-139">대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-139">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="810d4-140">구성 파일</span><span class="sxs-lookup"><span data-stu-id="810d4-140">Configuration files</span></span>

<span data-ttu-id="810d4-141">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-141">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="810d4-142">예제</span><span class="sxs-lookup"><span data-stu-id="810d4-142">Example</span></span>

<span data-ttu-id="810d4-143">다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="810d4-143">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="810d4-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="810d4-144">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="810d4-145">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="810d4-145">Network Settings Schema</span></span>](index.md)
