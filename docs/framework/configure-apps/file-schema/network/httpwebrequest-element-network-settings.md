---
title: <httpWebRequest> 요소 (네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 722b2f726c9085f6dee6bad82044da3011b98702
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169301"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="772df-102">\<httpWebRequest > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="772df-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="772df-103">웹 요청 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="772df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="772df-104">\<configuration></span></span>  
<span data-ttu-id="772df-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="772df-105">\<system.net></span></span>  
<span data-ttu-id="772df-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="772df-106">\<settings></span></span>  
<span data-ttu-id="772df-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="772df-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772df-108">구문</span><span class="sxs-lookup"><span data-stu-id="772df-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="772df-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="772df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="772df-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="772df-111">특성</span><span class="sxs-lookup"><span data-stu-id="772df-111">Attributes</span></span>  
  
|**<span data-ttu-id="772df-112">특성</span><span class="sxs-lookup"><span data-stu-id="772df-112">Attribute</span></span>**|**<span data-ttu-id="772df-113">설명</span><span class="sxs-lookup"><span data-stu-id="772df-113">Description</span></span>**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="772df-114">(킬로바이트), 응답 헤더의 최대 길이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="772df-115">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-115">The default is 64.</span></span> <span data-ttu-id="772df-116">값이-1 크기 제한이 응답 헤더에 적용 됩니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="772df-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="772df-117">(킬로바이트)는 오류 응답의 최대 길이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="772df-118">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-118">The default is 64.</span></span> <span data-ttu-id="772df-119">값이-1은 오류 응답에 크기 제한이 적용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="772df-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="772df-120">권한이 없는 오류 코드, 바이트에서에 대 한 응답에서 업로드할 경우의 최대 길이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="772df-121">기본값은 -1입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-121">The default is -1.</span></span> <span data-ttu-id="772df-122">-1은 업로드할 때 크기 제한이 적용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="772df-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="772df-123">안전 하지 않은 헤더를 구문 분석 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="772df-124">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="772df-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="772df-125">Child Elements</span></span>  
 <span data-ttu-id="772df-126">없음</span><span class="sxs-lookup"><span data-stu-id="772df-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="772df-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="772df-127">Parent Elements</span></span>  
  
|**<span data-ttu-id="772df-128">요소</span><span class="sxs-lookup"><span data-stu-id="772df-128">Element</span></span>**|**<span data-ttu-id="772df-129">설명</span><span class="sxs-lookup"><span data-stu-id="772df-129">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="772df-130">설정</span><span class="sxs-lookup"><span data-stu-id="772df-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="772df-131"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="772df-132">설명</span><span class="sxs-lookup"><span data-stu-id="772df-132">Remarks</span></span>  
 <span data-ttu-id="772df-133">기본적으로.NET Framework URI 구문 분석에 대 한 RFC 2616 엄격 하 게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="772df-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="772df-134">일부 서버 응답 하면는 허용 되지 않는 필드에 제어 문자를 포함할 수 있습니다 합니다 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> throw 하는 메서드를 <xref:System.Net.WebException>입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="772df-135">하는 경우 **useUnsafeHeaderParsing** 로 설정 된 **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> 있지만 경우에 throw 하지 것입니다, 응용 프로그램은 여러 형태의 URI 구문 분석 공격에 취약 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="772df-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="772df-136">가장 적합 한 솔루션 응답 제어 문자가 포함 되지 않습니다 있도록 서버를 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="772df-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="772df-137">Configuration Files</span></span>  
 <span data-ttu-id="772df-138">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="772df-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="772df-139">예제</span><span class="sxs-lookup"><span data-stu-id="772df-139">Example</span></span>  
 <span data-ttu-id="772df-140">다음 예제에서는 큰 값을 지정 하는 방법 보다 일반적인 최대 헤더 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="772df-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="772df-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="772df-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="772df-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="772df-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
