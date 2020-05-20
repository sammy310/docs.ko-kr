---
title: _CorValidateImage 함수
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
ms.openlocfilehash: 8841fab0517353849ef99594bcbd03dda772c766
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616504"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="d0e7f-102">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="d0e7f-102">_CorValidateImage Function</span></span>
<span data-ttu-id="d0e7f-103">관리 되는 모듈 이미지의 유효성을 검사 하 고, 운영 체제 로더가 로드 된 후이를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e7f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0e7f-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0e7f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0e7f-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="d0e7f-106">진행 관리 코드로 유효성을 검사할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="d0e7f-107">이미지가 이미 메모리에 로드 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="d0e7f-108">진행 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0e7f-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d0e7f-109">Return Value</span></span>  
 <span data-ttu-id="d0e7f-110">이 함수는 `E_INVALIDARG` `E_OUTOFMEMORY` `E_UNEXPECTED` 다음 값 뿐만 아니라 표준 값,, 및를 반환 합니다 `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="d0e7f-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="d0e7f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d0e7f-111">Return value</span></span>|<span data-ttu-id="d0e7f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d0e7f-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="d0e7f-113">이미지가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-113">The image is invalid.</span></span> <span data-ttu-id="d0e7f-114">이 값에는 HRESULT 0xC000007BL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="d0e7f-115">이미지가 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-115">The image is valid.</span></span> <span data-ttu-id="d0e7f-116">이 값에는 HRESULT 0x00000000L이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e7f-117">설명</span><span class="sxs-lookup"><span data-stu-id="d0e7f-117">Remarks</span></span>  
 <span data-ttu-id="d0e7f-118">Windows XP 이상 버전에서 운영 체제 로더는 COFF (common object file format) 헤더의 COM 설명자 디렉터리 비트를 검사 하 여 관리 되는 모듈을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="d0e7f-119">설정 비트는 관리 되는 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="d0e7f-120">로더가 관리 되는 모듈을 감지 하면 Mscoree.dll을 로드 하 고를 호출 하 여 `_CorValidateImage` 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="d0e7f-121">이미지가 올바른 관리 되는 모듈 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="d0e7f-122">이미지의 진입점을 CLR (공용 언어 런타임)의 진입점으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="d0e7f-123">64 비트 버전의 Windows에서는 PE32에서 PE32 + 형식으로 변환 하 여 메모리에 있는 이미지를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="d0e7f-124">관리 되는 모듈 이미지가 로드 될 때 로더에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="d0e7f-125">실행 가능 이미지의 경우 운영 체제 로더에서 실행 파일에 지정 된 진입점에 관계 없이 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="d0e7f-126">DLL 어셈블리 이미지의 경우 로더는 [_CorDllMain](cordllmain-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-126">For DLL assembly images, the loader calls the [_CorDllMain](cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="d0e7f-127">`_CorExeMain`또는 `_CorDllMain` 에서는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="d0e7f-128">CLR을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="d0e7f-129">어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="d0e7f-130">실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-130">Begins execution.</span></span>  
  
 <span data-ttu-id="d0e7f-131">로더는 관리 되는 모듈 이미지가 언로드될 때 [_CorImageUnloading](corimageunloading-function.md) 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-131">The loader calls the [_CorImageUnloading](corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="d0e7f-132">그러나이 함수는 아무 작업도 수행 하지 않습니다. 만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0e7f-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0e7f-133">Requirements</span></span>  
 <span data-ttu-id="d0e7f-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0e7f-135">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d0e7f-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0e7f-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0e7f-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0e7f-137">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0e7f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e7f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0e7f-138">See also</span></span>

- [<span data-ttu-id="d0e7f-139">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d0e7f-139">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
