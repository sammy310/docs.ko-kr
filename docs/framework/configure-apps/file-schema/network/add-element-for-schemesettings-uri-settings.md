---
title: schemeSettings의 <add> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: efd52557ea8b617a39e685ff8ad69bab01322a7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699600"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="af113-102">schemeSettings에 대 한 \<add > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="af113-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="af113-103">구성표 이름에 대 한 구성표 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af113-103">Adds a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="af113-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="af113-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="af113-105">&nbsp; @ no__t[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="af113-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="af113-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="af113-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="af113-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="af113-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af113-108">구문</span><span class="sxs-lookup"><span data-stu-id="af113-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af113-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="af113-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af113-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="af113-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af113-111">특성</span><span class="sxs-lookup"><span data-stu-id="af113-111">Attributes</span></span>  
  
|<span data-ttu-id="af113-112">특성</span><span class="sxs-lookup"><span data-stu-id="af113-112">Attribute</span></span>|<span data-ttu-id="af113-113">설명</span><span class="sxs-lookup"><span data-stu-id="af113-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af113-114">name</span><span class="sxs-lookup"><span data-stu-id="af113-114">name</span></span>|<span data-ttu-id="af113-115">이 설정이 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af113-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="af113-116">유일 하 게 지원 되는 값은 name = "http" 및 name = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="af113-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="af113-117">{Attribute name} 특성도</span><span class="sxs-lookup"><span data-stu-id="af113-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="af113-118">값</span><span class="sxs-lookup"><span data-stu-id="af113-118">Value</span></span>|<span data-ttu-id="af113-119">설명</span><span class="sxs-lookup"><span data-stu-id="af113-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af113-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="af113-120">genericUriParserOptions</span></span>|<span data-ttu-id="af113-121">이 스키마에 대 한 파서 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="af113-121">The parser options for this scheme.</span></span> <span data-ttu-id="af113-122">유일 하 게 지원 되는 값은 genericUriParserOptions = "DontUnescapePathDotsAndSlashes"입니다.</span><span class="sxs-lookup"><span data-stu-id="af113-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af113-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="af113-123">Child Elements</span></span>  
 <span data-ttu-id="af113-124">없음</span><span class="sxs-lookup"><span data-stu-id="af113-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af113-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="af113-125">Parent Elements</span></span>  
  
|<span data-ttu-id="af113-126">요소</span><span class="sxs-lookup"><span data-stu-id="af113-126">Element</span></span>|<span data-ttu-id="af113-127">설명</span><span class="sxs-lookup"><span data-stu-id="af113-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af113-128">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="af113-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="af113-129">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af113-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af113-130">설명</span><span class="sxs-lookup"><span data-stu-id="af113-130">Remarks</span></span>  
 <span data-ttu-id="af113-131">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 백분율로 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="af113-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="af113-132">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af113-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="af113-133">이 URI에 전달 하는 경우 모듈까지 %를 처리 하지 못할 경우 인코딩된 문자를 올바르게, 서버에서 실행 되 고 다음 명령에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af113-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="af113-134">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af113-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="af113-135">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="af113-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="af113-136">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af113-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="af113-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="af113-137">Configuration Files</span></span>  
 <span data-ttu-id="af113-138">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af113-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af113-139">예제</span><span class="sxs-lookup"><span data-stu-id="af113-139">Example</span></span>  
 <span data-ttu-id="af113-140">다음 예제에서는 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않도록 지원 하기 위해 <xref:System.Uri> 클래스에서 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af113-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af113-141">참조</span><span class="sxs-lookup"><span data-stu-id="af113-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="af113-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="af113-142">Network Settings Schema</span></span>](index.md)
