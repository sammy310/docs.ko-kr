---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614686"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="395a7-101">경로 정규화의 변경</span><span class="sxs-lookup"><span data-stu-id="395a7-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="395a7-102">설명</span><span class="sxs-lookup"><span data-stu-id="395a7-102">Details</span></span>

<span data-ttu-id="395a7-103">.NET Framework 4.6.2를 대상으로 하는 앱부터 런타임이 경로를 정규화하는 방식이 변경되었습니다. 경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="395a7-104">정규화에는 일반적으로 다음이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-104">Normalization typically involves:</span></span>

- <span data-ttu-id="395a7-105">구성 요소 및 디렉터리 구분 기호 정규화</span><span class="sxs-lookup"><span data-stu-id="395a7-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="395a7-106">상대 경로에 현재 디렉터리 적용</span><span class="sxs-lookup"><span data-stu-id="395a7-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="395a7-107">경로의 상대 디렉터리(.) 또는 부모 디렉터리(..) 평가</span><span class="sxs-lookup"><span data-stu-id="395a7-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="395a7-108">지정된 문자 자르기</span><span class="sxs-lookup"><span data-stu-id="395a7-108">Trimming specified characters.</span></span>
<span data-ttu-id="395a7-109">.NET Framework 4.6.2를 대상으로 하는 앱부터는 경로 정규화의 다음 변경이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="395a7-110">런타임은 운영 체제의 [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) 함수를 지연시켜 경로를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="395a7-111">정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="395a7-112">완전 신뢰의 디바이스 경로 구문(`\\.\` 포함) 지원 및 mscorlib.dll `\\?\`에서 파일 I/O API 지원</span><span class="sxs-lookup"><span data-stu-id="395a7-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="395a7-113">런타임에서 디바이스 구문 경로가 유효한지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="395a7-114">대체 데이터 스트림에 액세스하기 위해 디바이스 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="395a7-115">이 변경 내용을 통해 메서드에서 이전에 액세스할 수 없는 경로에 액세스할 수 있게 되며 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="395a7-116">.NET Framework 4.6.1 이하 버전을 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 이러한 변경에 의해 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="395a7-117">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="395a7-117">Suggestion</span></span>

<span data-ttu-id="395a7-118">.NET Framework 4.6.2 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 정규화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="395a7-119">.NET Framework 4.6.1 이하를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 경로 정규화에 변경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="395a7-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="395a7-120">이름</span><span class="sxs-lookup"><span data-stu-id="395a7-120">Name</span></span>    | <span data-ttu-id="395a7-121">값</span><span class="sxs-lookup"><span data-stu-id="395a7-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="395a7-122">Scope</span><span class="sxs-lookup"><span data-stu-id="395a7-122">Scope</span></span>   | <span data-ttu-id="395a7-123">부</span><span class="sxs-lookup"><span data-stu-id="395a7-123">Minor</span></span>       |
| <span data-ttu-id="395a7-124">버전</span><span class="sxs-lookup"><span data-stu-id="395a7-124">Version</span></span> | <span data-ttu-id="395a7-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="395a7-125">4.6.2</span></span>       |
| <span data-ttu-id="395a7-126">형식</span><span class="sxs-lookup"><span data-stu-id="395a7-126">Type</span></span>    | <span data-ttu-id="395a7-127">대상 변경</span><span class="sxs-lookup"><span data-stu-id="395a7-127">Retargeting</span></span> |
