---
title: <schemeSettings> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697763"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="c0795-102">\<schemeSettings > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="c0795-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="c0795-103">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="c0795-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c0795-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c0795-105">&nbsp;&nbsp;[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c0795-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="c0795-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<schemeSettings >**</span><span class="sxs-lookup"><span data-stu-id="c0795-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0795-107">구문</span><span class="sxs-lookup"><span data-stu-id="c0795-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0795-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0795-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c0795-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0795-110">특성</span><span class="sxs-lookup"><span data-stu-id="c0795-110">Attributes</span></span>  
 <span data-ttu-id="c0795-111">없음</span><span class="sxs-lookup"><span data-stu-id="c0795-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0795-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0795-112">Child Elements</span></span>  
  
|<span data-ttu-id="c0795-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="c0795-113">**Element**</span></span>|<span data-ttu-id="c0795-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="c0795-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0795-115">add</span><span class="sxs-lookup"><span data-stu-id="c0795-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c0795-116">구성표 이름에 대 한 구성표 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="c0795-117">clear</span><span class="sxs-lookup"><span data-stu-id="c0795-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c0795-118">기존 구성표 설정을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="c0795-119">remove</span><span class="sxs-lookup"><span data-stu-id="c0795-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="c0795-120">구성표 이름에 대 한 구성표 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0795-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0795-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c0795-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="c0795-122">**Element**</span></span>|<span data-ttu-id="c0795-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="c0795-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0795-124">uri</span><span class="sxs-lookup"><span data-stu-id="c0795-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="c0795-125">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0795-126">주의</span><span class="sxs-lookup"><span data-stu-id="c0795-126">Remarks</span></span>  
 <span data-ttu-id="c0795-127">기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 백분율로 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="c0795-128">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c0795-129">이 URI에 전달 하는 경우 모듈까지 %를 처리 하지 못할 경우 인코딩된 문자를 올바르게, 서버에서 실행 되 고 다음 명령에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="c0795-130">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="c0795-131">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="c0795-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="c0795-132">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0795-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c0795-133">Configuration Files</span></span>  
 <span data-ttu-id="c0795-134">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0795-135">예제</span><span class="sxs-lookup"><span data-stu-id="c0795-135">Example</span></span>  
 <span data-ttu-id="c0795-136">다음 예제에서는 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않도록 지원 하기 위해 <xref:System.Uri> 클래스에서 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0795-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="c0795-137">요소 정보</span><span class="sxs-lookup"><span data-stu-id="c0795-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="c0795-138">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c0795-138">Namespace</span></span>|<span data-ttu-id="c0795-139">시스템</span><span class="sxs-lookup"><span data-stu-id="c0795-139">System</span></span>|  
|<span data-ttu-id="c0795-140">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="c0795-140">Schema Name</span></span>||  
|<span data-ttu-id="c0795-141">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="c0795-141">Validation File</span></span>||  
|<span data-ttu-id="c0795-142">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="c0795-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c0795-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0795-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="c0795-144">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c0795-144">Network Settings Schema</span></span>](index.md)
