---
title: <schemeSettings> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154649"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="14522-102">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="14522-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="14522-103">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="14522-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="14522-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="14522-105">&nbsp;&nbsp;[**\<우리>**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="14522-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="14522-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<구성표설정>**</span><span class="sxs-lookup"><span data-stu-id="14522-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14522-107">구문</span><span class="sxs-lookup"><span data-stu-id="14522-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14522-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14522-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14522-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14522-110">특성</span><span class="sxs-lookup"><span data-stu-id="14522-110">Attributes</span></span>  
 <span data-ttu-id="14522-111">None</span><span class="sxs-lookup"><span data-stu-id="14522-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14522-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14522-112">Child Elements</span></span>  
  
|<span data-ttu-id="14522-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="14522-113">**Element**</span></span>|<span data-ttu-id="14522-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="14522-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14522-115">추가</span><span class="sxs-lookup"><span data-stu-id="14522-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="14522-116">구성표 이름에 대한 구성표 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="14522-117">명확한</span><span class="sxs-lookup"><span data-stu-id="14522-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="14522-118">모든 기존 구성표 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="14522-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="14522-119">제거</span><span class="sxs-lookup"><span data-stu-id="14522-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="14522-120">구성표 이름에 대한 구성표 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14522-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14522-121">Parent Elements</span></span>  
  
|<span data-ttu-id="14522-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="14522-122">**Element**</span></span>|<span data-ttu-id="14522-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="14522-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14522-124">Uri</span><span class="sxs-lookup"><span data-stu-id="14522-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="14522-125">.NET Framework에서 균일한 리소스 식별자(URIs)를 사용하여 표현된 웹 주소를 처리하는 방법을 지정하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14522-126">설명</span><span class="sxs-lookup"><span data-stu-id="14522-126">Remarks</span></span>  
 <span data-ttu-id="14522-127">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스는 경로 압축을 실행하기 전에 인코딩된 경로 구분 기호%를 이스케이프해제합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="14522-128">이 메커니즘은 다음과 같은 공격에 대한 보안 메커니즘으로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="14522-129">이 URI가 인코딩된 문자를 올바르게 처리하지 않는 모듈로 전달되면 서버에서 다음 명령이 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="14522-130">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스 첫 번째 un-escapes 경로 구분 기호 를 적용 하 고 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="14522-131">위의 악의적인 URL을 클래스 <xref:System.Uri?displayProperty=nameWithType> 생성자로 전달하면 다음 URI가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14522-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="14522-132">이 기본 동작은 특정 구성표에 대한 schemeSettings 구성 옵션을 사용하여 이스케이프 해제 백% 인코딩된 경로 구분자를 사용하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="14522-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="14522-133">Configuration Files</span></span>  
 <span data-ttu-id="14522-134">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14522-135">예제</span><span class="sxs-lookup"><span data-stu-id="14522-135">Example</span></span>  
 <span data-ttu-id="14522-136">다음 예제에서는 http 체계에 <xref:System.Uri> 대 한 백분율 인코딩된 경로 구분 자를 이스케이프 하지 를 지원 하기 위해 클래스에서 사용 하는 구성을 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="14522-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="14522-137">요소 정보</span><span class="sxs-lookup"><span data-stu-id="14522-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="14522-138">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="14522-138">Namespace</span></span>|<span data-ttu-id="14522-139">시스템</span><span class="sxs-lookup"><span data-stu-id="14522-139">System</span></span>|  
|<span data-ttu-id="14522-140">Schema Name</span><span class="sxs-lookup"><span data-stu-id="14522-140">Schema Name</span></span>||  
|<span data-ttu-id="14522-141">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="14522-141">Validation File</span></span>||  
|<span data-ttu-id="14522-142">비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14522-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="14522-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14522-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="14522-144">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="14522-144">Network Settings Schema</span></span>](index.md)
