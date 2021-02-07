---
description: '자세히 알아보기: ICLRMetaHost:: GetVersionFromFile 메서드'
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
ms.openlocfilehash: 0122c4aba3b8454a84540b22e815c61a2cb25df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689055"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="71b59-103">ICLRMetaHost::GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="71b59-103">ICLRMetaHost::GetVersionFromFile Method</span></span>

<span data-ttu-id="71b59-104">파일 경로가 지정 된 경우 메타 데이터에 저장 된 어셈블리의 원래 .NET Framework 컴파일 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-104">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="71b59-105">이 메서드는 [GetFileVersion](getfileversion-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-105">This method supersedes the [GetFileVersion](getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b59-106">구문</span><span class="sxs-lookup"><span data-stu-id="71b59-106">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71b59-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71b59-107">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="71b59-108">진행 전체 어셈블리 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-108">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="71b59-109">제한이 메타 데이터에 저장 된 .NET Framework 컴파일 버전 ("v *A*" 형식)입니다. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="71b59-109">[out] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="71b59-110">*A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="71b59-111">이 문자열의 길이는 MAX_PATH로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-111">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71b59-112">이 출력은 C:\Windows\Microsoft.NET\Framework. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-112">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="71b59-113">예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *X*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-113">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="71b59-114">"V" 접두사는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-114">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="71b59-115">[in, out] `pwzbuffer` 버퍼 오버런을 방지 하기 위한의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-115">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71b59-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="71b59-116">Return Value</span></span>  

 <span data-ttu-id="71b59-117">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71b59-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71b59-118">HRESULT</span></span>|<span data-ttu-id="71b59-119">설명</span><span class="sxs-lookup"><span data-stu-id="71b59-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71b59-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="71b59-120">S_OK</span></span>|<span data-ttu-id="71b59-121">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="71b59-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="71b59-122">E_POINTER</span></span>|<span data-ttu-id="71b59-123">`pwzbuffer` 또는 `pcchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-123">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="71b59-124">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="71b59-124">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="71b59-125">버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-125">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71b59-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71b59-126">Requirements</span></span>  

 <span data-ttu-id="71b59-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71b59-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b59-128">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="71b59-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71b59-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71b59-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71b59-130">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b59-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b59-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71b59-131">See also</span></span>

- [<span data-ttu-id="71b59-132">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71b59-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="71b59-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="71b59-133">Hosting</span></span>](index.md)
