---
title: GetHistoryFileDirectory 함수
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724440"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="d528b-102">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="d528b-102">GetHistoryFileDirectory Function</span></span>

<span data-ttu-id="d528b-103">응용 프로그램 기록 디렉터리의 경로를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d528b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d528b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d528b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d528b-105">Parameters</span></span>  

 `wzDir`  
 <span data-ttu-id="d528b-106">제한이 응용 프로그램 기록 디렉터리의 경로를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="d528b-107">[in, out] 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d528b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d528b-108">Return Value</span></span>  

 <span data-ttu-id="d528b-109">이 메서드는 Winerror.h 파일에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="d528b-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="d528b-110">Return code</span></span>|<span data-ttu-id="d528b-111">설명</span><span class="sxs-lookup"><span data-stu-id="d528b-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d528b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d528b-112">S_OK</span></span>|<span data-ttu-id="d528b-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d528b-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d528b-114">E_INVALIDARG</span></span>|<span data-ttu-id="d528b-115">`wzDir` 또는 `pdwSize` 이 null 이거나 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d528b-116">설명</span><span class="sxs-lookup"><span data-stu-id="d528b-116">Remarks</span></span>  

 <span data-ttu-id="d528b-117">성공적으로 완료 되 면 `pdwSize` 인수는 경로 문자열의 길이로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d528b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d528b-118">Requirements</span></span>  

 <span data-ttu-id="d528b-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d528b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d528b-120">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d528b-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d528b-121">**라이브러리:** Fusion.dll 및 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="d528b-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d528b-122">Mscorwks.dll 대신 Fusion.dll를 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d528b-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d528b-123">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d528b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d528b-124">참조</span><span class="sxs-lookup"><span data-stu-id="d528b-124">See also</span></span>

- [<span data-ttu-id="d528b-125">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="d528b-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="d528b-126">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="d528b-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="d528b-127">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d528b-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
