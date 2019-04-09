---
title: <add> SchemeSettings (Uri 설정)에 대 한
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: e7606a1185d406384a926ca4dcb7c42586461574
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139934"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="900ee-102">\<추가 > schemeSettings (Uri 설정)에 대 한</span><span class="sxs-lookup"><span data-stu-id="900ee-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="900ee-103">스키마 이름에 대 한 스키마 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="900ee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="900ee-104">\<configuration></span></span>  
<span data-ttu-id="900ee-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="900ee-105">\<uri></span></span>  
<span data-ttu-id="900ee-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="900ee-106">\<schemeSettings></span></span>  
<span data-ttu-id="900ee-107">\<add></span><span class="sxs-lookup"><span data-stu-id="900ee-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="900ee-108">구문</span><span class="sxs-lookup"><span data-stu-id="900ee-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="900ee-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="900ee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="900ee-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="900ee-111">특성</span><span class="sxs-lookup"><span data-stu-id="900ee-111">Attributes</span></span>  
  
|<span data-ttu-id="900ee-112">특성</span><span class="sxs-lookup"><span data-stu-id="900ee-112">Attribute</span></span>|<span data-ttu-id="900ee-113">설명</span><span class="sxs-lookup"><span data-stu-id="900ee-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="900ee-114">name</span><span class="sxs-lookup"><span data-stu-id="900ee-114">name</span></span>|<span data-ttu-id="900ee-115">이 설정은 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="900ee-116">이름과 "http"만 지원 되는 값 이름 = = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="900ee-117">{0} 특성 이름} 특성</span><span class="sxs-lookup"><span data-stu-id="900ee-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="900ee-118">값</span><span class="sxs-lookup"><span data-stu-id="900ee-118">Value</span></span>|<span data-ttu-id="900ee-119">설명</span><span class="sxs-lookup"><span data-stu-id="900ee-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="900ee-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="900ee-120">genericUriParserOptions</span></span>|<span data-ttu-id="900ee-121">이 스키마에 대 한 파서 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-121">The parser options for this scheme.</span></span> <span data-ttu-id="900ee-122">지원 되는 값은 genericUriParserOptions만 = "DontUnescapePathDotsAndSlashes"입니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="900ee-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="900ee-123">Child Elements</span></span>  
 <span data-ttu-id="900ee-124">없음</span><span class="sxs-lookup"><span data-stu-id="900ee-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="900ee-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="900ee-125">Parent Elements</span></span>  
  
|<span data-ttu-id="900ee-126">요소</span><span class="sxs-lookup"><span data-stu-id="900ee-126">Element</span></span>|<span data-ttu-id="900ee-127">설명</span><span class="sxs-lookup"><span data-stu-id="900ee-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="900ee-128">\<schemeSettings > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="900ee-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="900ee-129">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="900ee-130">설명</span><span class="sxs-lookup"><span data-stu-id="900ee-130">Remarks</span></span>  
 <span data-ttu-id="900ee-131">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 백분율로 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="900ee-132">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="900ee-133">이 URI에 전달 하는 경우 모듈까지 %를 처리 하지 못할 경우 인코딩된 문자를 올바르게, 서버에서 실행 되 고 다음 명령에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="900ee-134">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="900ee-135">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="900ee-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="900ee-136">SchemeSettings 구성 옵션을 사용 하 여 특정 스키마에 대 한 이스케이프 해제 백분율로 인코딩된 경로 구분 되지에이 기본 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="900ee-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="900ee-137">Configuration Files</span></span>  
 <span data-ttu-id="900ee-138">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="900ee-139">예제</span><span class="sxs-lookup"><span data-stu-id="900ee-139">Example</span></span>  
 <span data-ttu-id="900ee-140">다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> http 체계에 대 한 백분율로 인코딩된 경로 구분 기호를 이스케이프 하지 않아도 되도록 지원 하기 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="900ee-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="900ee-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="900ee-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="900ee-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="900ee-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
