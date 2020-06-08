---
title: <httpWebRequest> 요소(네트워크 설정)
description: <httpWebRequest>네트워크 설정 요소는 .NET Framework에서 웹 요청 매개 변수를 사용자 지정 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 59ab425dcef8ac5283035910a9d78a89a16be8b1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504591"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="94b9c-103">\<httpWebRequest> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="94b9c-103">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="94b9c-104">웹 요청 매개 변수를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="94b9c-105">구문</span><span class="sxs-lookup"><span data-stu-id="94b9c-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94b9c-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="94b9c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="94b9c-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94b9c-108">특성</span><span class="sxs-lookup"><span data-stu-id="94b9c-108">Attributes</span></span>  
  
|<span data-ttu-id="94b9c-109">**특성**</span><span class="sxs-lookup"><span data-stu-id="94b9c-109">**Attribute**</span></span>|<span data-ttu-id="94b9c-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="94b9c-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="94b9c-111">응답 헤더의 최대 길이 (kb)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="94b9c-112">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-112">The default is 64.</span></span> <span data-ttu-id="94b9c-113">값이-1 이면 응답 헤더에 크기 제한이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="94b9c-114">오류 응답의 최대 길이 (kb)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="94b9c-115">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-115">The default is 64.</span></span> <span data-ttu-id="94b9c-116">값이-1 이면 오류 응답에 크기 제한이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="94b9c-117">승인 되지 않은 오류 코드에 대 한 응답으로 업로드의 최대 길이 (바이트)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="94b9c-118">기본값은 -1입니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-118">The default is -1.</span></span> <span data-ttu-id="94b9c-119">-1은 업로드할 때 크기 제한이 적용되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="94b9c-120">안전 하지 않은 헤더 구문 분석을 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="94b9c-121">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94b9c-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="94b9c-122">Child Elements</span></span>  
 <span data-ttu-id="94b9c-123">없음</span><span class="sxs-lookup"><span data-stu-id="94b9c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94b9c-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="94b9c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="94b9c-125">**요소**</span><span class="sxs-lookup"><span data-stu-id="94b9c-125">**Element**</span></span>|<span data-ttu-id="94b9c-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="94b9c-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="94b9c-127">설정</span><span class="sxs-lookup"><span data-stu-id="94b9c-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="94b9c-128"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94b9c-129">설명</span><span class="sxs-lookup"><span data-stu-id="94b9c-129">Remarks</span></span>  
 <span data-ttu-id="94b9c-130">기본적으로 .NET Framework는 URI 구문 분석에 대해 RFC 2616를 엄격 하 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="94b9c-131">일부 서버 응답에는 허용 되지 않는 필드의 제어 문자가 포함 될 수 있으며,이로 인해 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> 메서드에서이 throw 됩니다 <xref:System.Net.WebException> .</span><span class="sxs-lookup"><span data-stu-id="94b9c-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="94b9c-132">**Useunsafeheaderparsing 분석이** **true**로 설정 된 경우 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> 이 경우가 throw 되지 않지만 응용 프로그램은 다양 한 형식의 URI 구문 분석 공격에 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="94b9c-133">가장 좋은 방법은 응답에 제어 문자가 포함 되지 않도록 서버를 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="94b9c-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="94b9c-134">Configuration Files</span></span>  
 <span data-ttu-id="94b9c-135">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94b9c-136">예제</span><span class="sxs-lookup"><span data-stu-id="94b9c-136">Example</span></span>  
 <span data-ttu-id="94b9c-137">다음 예제에서는 표준 최대 헤더 길이 보다 큰를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94b9c-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="94b9c-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94b9c-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="94b9c-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="94b9c-139">Network Settings Schema</span></span>](index.md)
