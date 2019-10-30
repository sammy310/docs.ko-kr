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
ms.openlocfilehash: 8fc2abd0728115edbbfae42958d8013029523ed1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111366"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="fd886-102">ICLRDebuggingLibraryProvider::ProvideLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="fd886-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>

<span data-ttu-id="fd886-103">CLR (공용 언어 런타임) 버전별 디버깅 라이브러리를 요청 시 배치 하 고 로드할 수 있도록 하는 라이브러리 공급자 콜백 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd886-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd886-104">Syntax</span></span>

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a><span data-ttu-id="fd886-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd886-105">Parameters</span></span>

`pwszFilename` \
<span data-ttu-id="fd886-106">진행 요청 되는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-106">[in] The name of the module being requested.</span></span>

`dwTimestamp` \
<span data-ttu-id="fd886-107">진행 PE 파일의 COFF 파일 헤더에 저장 된 날짜 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>

`pLibraryProvider` \
<span data-ttu-id="fd886-108">진행 PE 파일의 COFF 선택적 파일 헤더에 저장 된 `SizeOfImage` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>

`hModule` \
<span data-ttu-id="fd886-109">제한이 요청 된 모듈에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-109">[out] The handle to the requested module.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd886-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd886-110">Return Value</span></span>

<span data-ttu-id="fd886-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="fd886-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd886-112">HRESULT</span></span>|<span data-ttu-id="fd886-113">설명</span><span class="sxs-lookup"><span data-stu-id="fd886-113">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="fd886-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd886-114">S_OK</span></span>|<span data-ttu-id="fd886-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-115">The method completed successfully.</span></span>|

## <a name="exceptions"></a><span data-ttu-id="fd886-116">예외</span><span class="sxs-lookup"><span data-stu-id="fd886-116">Exceptions</span></span>

## <a name="remarks"></a><span data-ttu-id="fd886-117">주의</span><span class="sxs-lookup"><span data-stu-id="fd886-117">Remarks</span></span>

<span data-ttu-id="fd886-118">`ProvideLibrary`를 사용 하면 디버거가 mscordbi.dll 및 mscordacwks와 같은 특정 CLR 파일을 디버깅 하는 데 필요한 모듈을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="fd886-119">[ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) 메서드를 호출할 때까지 모듈 핸들은 유효한 상태로 유지 되어야 합니다 .이 경우에는 호출자가 핸들을 해제할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>

<span data-ttu-id="fd886-120">디버거는 사용 가능한 모든 방법을 사용 하 여 디버깅 모듈을 찾거나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-120">The debugger may use any available means to locate or procure the debugging module.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd886-121">이 기능을 통해 API 호출자는 실행 파일 및 악성 코드가 포함 된 모듈을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="fd886-122">보안 예방 조치로 서 호출자는 `ProvideLibrary`를 사용 하 여 자신을 직접 실행 하지 않는 코드를 배포 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>
>
> <span data-ttu-id="fd886-123">Mscordbi.dll 또는 mscordacwks와 같은 이미 릴리스된 라이브러리에서 심각한 보안 문제가 발견 되 면 shim을 패치 하 여 잘못 된 버전의 파일을 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="fd886-124">그러면 shim은 패치 된 버전의 파일에 대 한 요청을 발급 하 고 요청에 대 한 응답으로 제공 된 경우 잘못 된 버전을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="fd886-125">이는 사용자가 새 버전의 shim에 패치를 적용 한 경우에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="fd886-126">패치가 적용 되지 않은 버전은 취약 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd886-126">Unpatched versions will remain vulnerable.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd886-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd886-127">Requirements</span></span>

<span data-ttu-id="fd886-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd886-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="fd886-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd886-129">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="fd886-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd886-130">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="fd886-131">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd886-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fd886-132">참조</span><span class="sxs-lookup"><span data-stu-id="fd886-132">See also</span></span>

- [<span data-ttu-id="fd886-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd886-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd886-134">디버깅</span><span class="sxs-lookup"><span data-stu-id="fd886-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
