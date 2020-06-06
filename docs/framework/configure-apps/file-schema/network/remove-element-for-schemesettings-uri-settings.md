---
title: schemeSettings의 <remove> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: faf254174527ea74638442a139841eb2365d1e5d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089156"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="bcbe7-102">schemeSettings의 \<remove> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="bcbe7-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="bcbe7-103">구성표 이름에 대 한 구성표 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="bcbe7-104">구문</span><span class="sxs-lookup"><span data-stu-id="bcbe7-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcbe7-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bcbe7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bcbe7-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcbe7-107">특성</span><span class="sxs-lookup"><span data-stu-id="bcbe7-107">Attributes</span></span>  
  
|<span data-ttu-id="bcbe7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="bcbe7-108">Attribute</span></span>|<span data-ttu-id="bcbe7-109">Description</span><span class="sxs-lookup"><span data-stu-id="bcbe7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcbe7-110">name</span><span class="sxs-lookup"><span data-stu-id="bcbe7-110">name</span></span>|<span data-ttu-id="bcbe7-111">이 설정이 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="bcbe7-112">유일 하 게 지원 되는 값은 name = "http" 및 name = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcbe7-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bcbe7-113">Child Elements</span></span>  
 <span data-ttu-id="bcbe7-114">없음</span><span class="sxs-lookup"><span data-stu-id="bcbe7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcbe7-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bcbe7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bcbe7-116">요소</span><span class="sxs-lookup"><span data-stu-id="bcbe7-116">Element</span></span>|<span data-ttu-id="bcbe7-117">Description</span><span class="sxs-lookup"><span data-stu-id="bcbe7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcbe7-118">\<schemeSettings>요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="bcbe7-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="bcbe7-119">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcbe7-120">설명</span><span class="sxs-lookup"><span data-stu-id="bcbe7-120">Remarks</span></span>  
 <span data-ttu-id="bcbe7-121">기본적으로 클래스는 <xref:System.Uri?displayProperty=nameWithType> 경로 압축을 실행 하기 전에 인코딩된 경로 구분 기호 비율을 이스케이프 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="bcbe7-122">이는 다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="bcbe7-123">% 인코딩된 문자를 올바르게 처리 하지 않는 모듈에이 URI가 전달 되 면 서버에서 다음 명령을 실행 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="bcbe7-124">따라서 <xref:System.Uri?displayProperty=nameWithType> 클래스는 먼저 경로 구분 기호를 이스케이프 해제 한 후 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="bcbe7-125">위의 악성 URL을 클래스 생성자에 전달 하면 <xref:System.Uri?displayProperty=nameWithType> 다음 URI가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="bcbe7-126">이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bcbe7-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bcbe7-127">Configuration Files</span></span>  
 <span data-ttu-id="bcbe7-128">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcbe7-129">예제</span><span class="sxs-lookup"><span data-stu-id="bcbe7-129">Example</span></span>  
 <span data-ttu-id="bcbe7-130">다음 예제에서는 <xref:System.Uri> 클래스에서 http 체계의 스키마 설정을 제거 하는 데 사용 하는 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcbe7-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcbe7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcbe7-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="bcbe7-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bcbe7-132">Network Settings Schema</span></span>](index.md)
