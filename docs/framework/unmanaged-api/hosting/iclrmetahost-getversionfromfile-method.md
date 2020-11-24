---
title: ICLRMetaHost::GetVersionFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: f5e0ead41ebd13c259c24fa0c02bcc9a3b33e0fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689448"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="ca495-102">ICLRMetaHost::GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="ca495-102">ICLRMetaHost::GetVersionFromFile Method</span></span>

<span data-ttu-id="ca495-103">파일 경로가 지정 된 경우 메타 데이터에 저장 된 어셈블리의 원래 .NET Framework 컴파일 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="ca495-104">이 메서드는 [GetFileVersion](getfileversion-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-104">This method supersedes the [GetFileVersion](getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca495-105">구문</span><span class="sxs-lookup"><span data-stu-id="ca495-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca495-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca495-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="ca495-107">진행 전체 어셈블리 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="ca495-108">제한이 메타 데이터에 저장 된 .NET Framework 컴파일 버전 ("v *A*" 형식)입니다. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="ca495-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="ca495-109">*A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="ca495-110">이 문자열의 길이는 MAX_PATH로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca495-111">이 출력은 C:\Windows\Microsoft.NET\Framework. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="ca495-112">예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *X*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="ca495-113">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="ca495-114">[in, out] `pwzbuffer` 버퍼 오버런을 방지 하기 위한의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca495-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="ca495-115">Return Value</span></span>  

 <span data-ttu-id="ca495-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ca495-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca495-117">HRESULT</span></span>|<span data-ttu-id="ca495-118">설명</span><span class="sxs-lookup"><span data-stu-id="ca495-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca495-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca495-119">S_OK</span></span>|<span data-ttu-id="ca495-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="ca495-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ca495-121">E_POINTER</span></span>|<span data-ttu-id="ca495-122">`pwzbuffer` 또는 `pcchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="ca495-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="ca495-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="ca495-124">버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca495-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca495-125">Requirements</span></span>  

 <span data-ttu-id="ca495-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca495-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca495-127">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ca495-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ca495-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca495-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca495-129">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca495-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca495-130">참조</span><span class="sxs-lookup"><span data-stu-id="ca495-130">See also</span></span>

- [<span data-ttu-id="ca495-131">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca495-131">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="ca495-132">호스팅</span><span class="sxs-lookup"><span data-stu-id="ca495-132">Hosting</span></span>](index.md)
