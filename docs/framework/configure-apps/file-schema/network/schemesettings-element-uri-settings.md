---
description: '다음에 대 한 자세한 정보: <schemeSettings> 요소 (Uri 설정)'
title: <schemeSettings> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 218676c10a8acaa79c2eb2146214e77beee9a972
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698442"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="b734f-103">\<schemeSettings> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="b734f-103">\<schemeSettings> Element (Uri Settings)</span></span>

<span data-ttu-id="b734f-104">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-104">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="b734f-105">구문</span><span class="sxs-lookup"><span data-stu-id="b734f-105">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b734f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b734f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b734f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b734f-108">특성</span><span class="sxs-lookup"><span data-stu-id="b734f-108">Attributes</span></span>  

 <span data-ttu-id="b734f-109">None</span><span class="sxs-lookup"><span data-stu-id="b734f-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b734f-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b734f-110">Child Elements</span></span>  
  
|<span data-ttu-id="b734f-111">**요소**</span><span class="sxs-lookup"><span data-stu-id="b734f-111">**Element**</span></span>|<span data-ttu-id="b734f-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="b734f-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b734f-113">add</span><span class="sxs-lookup"><span data-stu-id="b734f-113">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="b734f-114">구성표 이름에 대 한 구성표 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-114">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="b734f-115">clear</span><span class="sxs-lookup"><span data-stu-id="b734f-115">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="b734f-116">기존 구성표 설정을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-116">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="b734f-117">remove</span><span class="sxs-lookup"><span data-stu-id="b734f-117">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="b734f-118">구성표 이름에 대 한 구성표 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-118">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b734f-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b734f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b734f-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="b734f-120">**Element**</span></span>|<span data-ttu-id="b734f-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="b734f-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b734f-122">uri</span><span class="sxs-lookup"><span data-stu-id="b734f-122">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="b734f-123">.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-123">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b734f-124">설명</span><span class="sxs-lookup"><span data-stu-id="b734f-124">Remarks</span></span>  

 <span data-ttu-id="b734f-125">기본적으로 클래스는 <xref:System.Uri?displayProperty=nameWithType> 경로 압축을 실행 하기 전에 인코딩된 경로 구분 기호 비율을 이스케이프 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b734f-126">이는 다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b734f-127">% 인코딩된 문자를 올바르게 처리 하지 않는 모듈에이 URI가 전달 되 면 서버에서 다음 명령을 실행 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b734f-128">따라서 <xref:System.Uri?displayProperty=nameWithType> 클래스는 먼저 경로 구분 기호를 이스케이프 해제 한 후 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b734f-129">위의 악성 URL을 클래스 생성자에 전달 하면 <xref:System.Uri?displayProperty=nameWithType> 다음 URI가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b734f-130">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b734f-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b734f-131">Configuration Files</span></span>  

 <span data-ttu-id="b734f-132">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b734f-133">예제</span><span class="sxs-lookup"><span data-stu-id="b734f-133">Example</span></span>  

 <span data-ttu-id="b734f-134">다음 예제에서는 <xref:System.Uri> http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않도록 지원 하기 위해 클래스에서 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b734f-134">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="b734f-135">요소 정보</span><span class="sxs-lookup"><span data-stu-id="b734f-135">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="b734f-136">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b734f-136">Namespace</span></span>|<span data-ttu-id="b734f-137">시스템</span><span class="sxs-lookup"><span data-stu-id="b734f-137">System</span></span>|  
|<span data-ttu-id="b734f-138">Schema Name</span><span class="sxs-lookup"><span data-stu-id="b734f-138">Schema Name</span></span>||  
|<span data-ttu-id="b734f-139">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="b734f-139">Validation File</span></span>||  
|<span data-ttu-id="b734f-140">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="b734f-140">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="b734f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b734f-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="b734f-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b734f-142">Network Settings Schema</span></span>](index.md)
