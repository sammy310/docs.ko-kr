---
description: '자세한 정보: <add> schemeSettings 요소에 대 한 요소 (Uri 설정)'
title: schemeSettings의 <add> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: c372577af1c7fbfe669455b50c8b55c82da4fc52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698623"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="5a7f3-103">schemeSettings의 \<add> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="5a7f3-103">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="5a7f3-104">구성표 이름에 대 한 구성표 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-104">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="5a7f3-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a7f3-105">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a7f3-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a7f3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5a7f3-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a7f3-108">특성</span><span class="sxs-lookup"><span data-stu-id="5a7f3-108">Attributes</span></span>  
  
|<span data-ttu-id="5a7f3-109">attribute</span><span class="sxs-lookup"><span data-stu-id="5a7f3-109">Attribute</span></span>|<span data-ttu-id="5a7f3-110">설명</span><span class="sxs-lookup"><span data-stu-id="5a7f3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a7f3-111">name</span><span class="sxs-lookup"><span data-stu-id="5a7f3-111">name</span></span>|<span data-ttu-id="5a7f3-112">이 설정이 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-112">The scheme name for which this setting applies.</span></span> <span data-ttu-id="5a7f3-113">유일 하 게 지원 되는 값은 name = "http" 및 name = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-113">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="5a7f3-114">{Attribute name} 특성도</span><span class="sxs-lookup"><span data-stu-id="5a7f3-114">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="5a7f3-115">값</span><span class="sxs-lookup"><span data-stu-id="5a7f3-115">Value</span></span>|<span data-ttu-id="5a7f3-116">설명</span><span class="sxs-lookup"><span data-stu-id="5a7f3-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a7f3-117">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="5a7f3-117">genericUriParserOptions</span></span>|<span data-ttu-id="5a7f3-118">이 스키마에 대 한 파서 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-118">The parser options for this scheme.</span></span> <span data-ttu-id="5a7f3-119">유일 하 게 지원 되는 값은 genericUriParserOptions = "DontUnescapePathDotsAndSlashes"입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-119">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a7f3-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a7f3-120">Child Elements</span></span>  

 <span data-ttu-id="5a7f3-121">없음</span><span class="sxs-lookup"><span data-stu-id="5a7f3-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a7f3-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a7f3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5a7f3-123">요소</span><span class="sxs-lookup"><span data-stu-id="5a7f3-123">Element</span></span>|<span data-ttu-id="5a7f3-124">설명</span><span class="sxs-lookup"><span data-stu-id="5a7f3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a7f3-125">\<schemeSettings> 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="5a7f3-125">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="5a7f3-126">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-126">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a7f3-127">설명</span><span class="sxs-lookup"><span data-stu-id="5a7f3-127">Remarks</span></span>  

 <span data-ttu-id="5a7f3-128">기본적으로 클래스는 <xref:System.Uri?displayProperty=nameWithType> 경로 압축을 실행 하기 전에 인코딩된 경로 구분 기호 비율을 이스케이프 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-128">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="5a7f3-129">이는 다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-129">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="5a7f3-130">% 인코딩된 문자를 올바르게 처리 하지 않는 모듈에이 URI가 전달 되 면 서버에서 다음 명령을 실행 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-130">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="5a7f3-131">따라서 <xref:System.Uri?displayProperty=nameWithType> 클래스는 먼저 경로 구분 기호를 이스케이프 해제 한 후 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-131">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="5a7f3-132">위의 악성 URL을 클래스 생성자에 전달 하면 <xref:System.Uri?displayProperty=nameWithType> 다음 URI가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-132">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="5a7f3-133">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-133">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5a7f3-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5a7f3-134">Configuration Files</span></span>  

 <span data-ttu-id="5a7f3-135">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a7f3-136">예제</span><span class="sxs-lookup"><span data-stu-id="5a7f3-136">Example</span></span>  

 <span data-ttu-id="5a7f3-137">다음 예제에서는 <xref:System.Uri> http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않도록 지원 하기 위해 클래스에서 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a7f3-137">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a7f3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a7f3-138">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="5a7f3-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5a7f3-139">Network Settings Schema</span></span>](index.md)
