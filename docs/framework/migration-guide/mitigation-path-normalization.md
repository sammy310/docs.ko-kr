---
title: '완화: 경로 정규화'
description: .NET Framework 4.6.2를 대상으로 하는 앱부터 .NET Framework의 경로 정규화가 변경되는 방식에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 89dcc46d9f266ffd3635dc0cc02b634720356eda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475218"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="8ed68-103">완화: 경로 정규화</span><span class="sxs-lookup"><span data-stu-id="8ed68-103">Mitigation: Path Normalization</span></span>
<span data-ttu-id="8ed68-104">.NET Framework 4.6.2를 대상으로 하는 앱부터 .NET Framework의 경로 정규화가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-104">Starting with apps that target .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="8ed68-105">경로 정규화란?</span><span class="sxs-lookup"><span data-stu-id="8ed68-105">What is path normalization?</span></span>  
 <span data-ttu-id="8ed68-106">경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-106">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="8ed68-107">정규화에는 일반적으로 다음이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-107">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="8ed68-108">구성 요소 및 디렉터리 구분 기호 정규화</span><span class="sxs-lookup"><span data-stu-id="8ed68-108">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="8ed68-109">상대 경로에 현재 디렉터리 적용</span><span class="sxs-lookup"><span data-stu-id="8ed68-109">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="8ed68-110">경로의 상대 디렉터리(`.`) 또는 부모 디렉터리(`..`) 평가</span><span class="sxs-lookup"><span data-stu-id="8ed68-110">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="8ed68-111">지정된 문자 자르기</span><span class="sxs-lookup"><span data-stu-id="8ed68-111">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="8ed68-112">변경 내용</span><span class="sxs-lookup"><span data-stu-id="8ed68-112">The changes</span></span>  
 <span data-ttu-id="8ed68-113">.NET Framework 4.6.2를 대상으로 하는 앱부터, 경로 정규화가 다음과 같이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-113">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="8ed68-114">런타임은 운영 체제의 [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) 함수를 지연시켜 경로를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-114">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="8ed68-115">정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-115">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="8ed68-116">완전 신뢰의 디바이스 경로 구문(`\\.\` 포함) 지원 및 mscorlib.dll `\\?\`에서 파일 I/O API 지원</span><span class="sxs-lookup"><span data-stu-id="8ed68-116">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="8ed68-117">런타임에서 디바이스 구문 경로가 유효한지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-117">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="8ed68-118">대체 데이터 스트림에 액세스하기 위해 디바이스 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-118">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8ed68-119">영향</span><span class="sxs-lookup"><span data-stu-id="8ed68-119">Impact</span></span>  

<span data-ttu-id="8ed68-120">.NET Framework 4.6.2 이상 버전을 대상으로 하는 앱의 경우 이러한 변경이 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-120">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="8ed68-121">이를 통해 메서드에서 이전에 액세스할 수 없는 경로에 액세스할 수 있게 되었으며 성능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-121">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="8ed68-122">.NET Framework 4.6.1 이하 버전을 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 이러한 변경에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-122">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8ed68-123">완화</span><span class="sxs-lookup"><span data-stu-id="8ed68-123">Mitigation</span></span>  
 <span data-ttu-id="8ed68-124">.NET Framework 4.6.2 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 정규화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-124">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="8ed68-125">.NET Framework 4.6.1 이하를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 애플리케이션 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 줄을 추가하여 경로 정규화에 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed68-125">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed68-126">참조</span><span class="sxs-lookup"><span data-stu-id="8ed68-126">See also</span></span>

- [<span data-ttu-id="8ed68-127">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="8ed68-127">Application compatibility</span></span>](application-compatibility.md)
