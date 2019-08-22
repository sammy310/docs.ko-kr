---
title: schemeSettings의 <clear> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 51c669aff767948523172aa075677ad3fb6478a2
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664174"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="42559-102">\<schemeSettings에 대 한 > 요소 지우기 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="42559-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="42559-103">기존 구성표 설정을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="42559-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="42559-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="42559-104">\<configuration></span></span>  
<span data-ttu-id="42559-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="42559-105">\<uri></span></span>  
<span data-ttu-id="42559-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="42559-106">\<schemeSettings></span></span>  
<span data-ttu-id="42559-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="42559-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42559-108">구문</span><span class="sxs-lookup"><span data-stu-id="42559-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42559-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42559-109">Attributes and Elements</span></span>  
 <span data-ttu-id="42559-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42559-111">특성</span><span class="sxs-lookup"><span data-stu-id="42559-111">Attributes</span></span>  
 <span data-ttu-id="42559-112">없음</span><span class="sxs-lookup"><span data-stu-id="42559-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42559-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42559-113">Child Elements</span></span>  
 <span data-ttu-id="42559-114">없음</span><span class="sxs-lookup"><span data-stu-id="42559-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42559-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42559-115">Parent Elements</span></span>  
  
|<span data-ttu-id="42559-116">요소</span><span class="sxs-lookup"><span data-stu-id="42559-116">Element</span></span>|<span data-ttu-id="42559-117">Description</span><span class="sxs-lookup"><span data-stu-id="42559-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42559-118">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="42559-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="42559-119">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42559-120">설명</span><span class="sxs-lookup"><span data-stu-id="42559-120">Remarks</span></span>  
 <span data-ttu-id="42559-121">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 백분율로 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="42559-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="42559-122">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="42559-123">이 URI에 전달 하는 경우 모듈까지 %를 처리 하지 못할 경우 인코딩된 문자를 올바르게, 서버에서 실행 되 고 다음 명령에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="42559-124">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="42559-125">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="42559-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="42559-126">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="42559-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="42559-127">Configuration Files</span></span>  
 <span data-ttu-id="42559-128">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42559-129">예제</span><span class="sxs-lookup"><span data-stu-id="42559-129">Example</span></span>  
 <span data-ttu-id="42559-130">다음 예제에서는 <xref:System.Uri> 클래스에서 사용 하는 구성을 보여 줍니다 .이 구성은 모든 체계 설정을 지운 다음 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않는 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42559-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="42559-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="42559-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="42559-132">Network Settings Schema</span></span>](index.md)
