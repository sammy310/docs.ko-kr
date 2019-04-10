---
title: ICLRDebuggingLibraryProvider::ProvideLibrary 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f5d44b6497e971e6d1ed030c043b91b88c070b6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218513"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="09f74-102">ICLRDebuggingLibraryProvider::ProvideLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="09f74-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="09f74-103">라이브러리 공급자 콜백 인터페이스를 공용 언어 런타임 (CLR) 버전별 디버깅 라이브러리 있고에 로드 된 요청 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09f74-104">구문</span><span class="sxs-lookup"><span data-stu-id="09f74-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09f74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09f74-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="09f74-106">[in] 요청 되는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="09f74-107">[in] PE 파일의 coff 파일에에서 저장 된 날짜 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="09f74-108">[in] `SizeOfImage` 필드 COFF 선택적 파일 헤더의 PE 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="09f74-109">[out] 요청된 된 모듈에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09f74-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="09f74-110">Return Value</span></span>  
 <span data-ttu-id="09f74-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09f74-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09f74-112">HRESULT</span></span>|<span data-ttu-id="09f74-113">설명</span><span class="sxs-lookup"><span data-stu-id="09f74-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09f74-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="09f74-114">S_OK</span></span>|<span data-ttu-id="09f74-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="09f74-116">예외</span><span class="sxs-lookup"><span data-stu-id="09f74-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09f74-117">설명</span><span class="sxs-lookup"><span data-stu-id="09f74-117">Remarks</span></span>  
 `ProvideLibrary` <span data-ttu-id="09f74-118">디버거를 mscordbi.dll mscordacwks.dll 등 특정 CLR 파일 디버깅에 필요한 모듈을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-118">allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="09f74-119">모듈 핸들에 대 한 호출 될 때까지 유효 해야 합니다 [iclrdebugging:: Canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) 는 해제할 수 있습니다 이며 이때 핸들을 해제 해야 하는 호출자의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="09f74-120">디버거를 찾거나 조달 디버깅 모듈에 사용 가능한 모든 수단을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09f74-121">이 기능을 사용 하면 API 호출자가 실행 파일 및 악의적인 코드가 포함 된 모듈을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="09f74-122">보안 조치로, 호출자에 게 사용 하지 않아야 `ProvideLibrary` 자체를 실행 하는 코드를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="09f74-123">심각한 보안 문제가 발견 되 면, mscordbi.dll 등 mscordacwks.dll, 이미 출시 된 라이브러리에 파일의 잘못 된 버전을 인식 하도록 shim은 패치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="09f74-124">Shim 수 되어 파일의 패치 버전에 대 한 요청을 발급 하 고 모든 요청에 대 한 응답에서 제공 하는 경우 잘못 된 버전을 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="09f74-125">사용자가 새 버전의 shim 패치 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="09f74-126">패치가 적용 되지 않은 버전 취약 한 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09f74-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09f74-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09f74-127">Requirements</span></span>  
 <span data-ttu-id="09f74-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09f74-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09f74-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09f74-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09f74-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09f74-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="09f74-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="09f74-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="09f74-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="09f74-132">See also</span></span>

- [<span data-ttu-id="09f74-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09f74-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="09f74-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="09f74-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
