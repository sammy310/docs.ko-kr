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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229629"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="60563-102">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="60563-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="60563-103">응용 프로그램 기록 디렉터리의 경로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="60563-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60563-104">구문</span><span class="sxs-lookup"><span data-stu-id="60563-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60563-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60563-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="60563-106">[out] 응용 프로그램 기록 디렉터리 경로 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="60563-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="60563-107">[out에서] 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="60563-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60563-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="60563-108">Return Value</span></span>  
 <span data-ttu-id="60563-109">이 메서드는 다음 값 외에도 WinError.h 파일에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="60563-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="60563-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="60563-110">Return code</span></span>|<span data-ttu-id="60563-111">설명</span><span class="sxs-lookup"><span data-stu-id="60563-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="60563-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="60563-112">S_OK</span></span>|<span data-ttu-id="60563-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="60563-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="60563-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="60563-114">E_INVALIDARG</span></span>|`wzDir` <span data-ttu-id="60563-115">또는 `pdwSize` 는 null 또는 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="60563-115">or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60563-116">설명</span><span class="sxs-lookup"><span data-stu-id="60563-116">Remarks</span></span>  
 <span data-ttu-id="60563-117">성공적으로 완료 되는 `pdwSize` 경로 문자열의 길이 인수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="60563-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60563-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60563-118">Requirements</span></span>  
 <span data-ttu-id="60563-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="60563-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60563-120">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="60563-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="60563-121">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="60563-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="60563-122">올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60563-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="60563-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="60563-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="60563-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="60563-124">See also</span></span>

- [<span data-ttu-id="60563-125">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="60563-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="60563-126">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="60563-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="60563-127">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="60563-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
