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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178212"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="32580-102">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="32580-102">_CorValidateImage Function</span></span>
<span data-ttu-id="32580-103">관리되는 모듈 이미지의 유효성을 검사하고 로드후 운영 체제 로더에 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32580-104">구문</span><span class="sxs-lookup"><span data-stu-id="32580-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32580-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32580-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="32580-106">【인】 관리 코드로 유효성을 검사하는 이미지의 시작 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32580-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="32580-107">이미지가 이미 메모리에 로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="32580-108">【인】 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32580-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32580-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="32580-109">Return Value</span></span>  
 <span data-ttu-id="32580-110">이 함수는 다음 `E_INVALIDARG` `E_OUTOFMEMORY`값뿐만 아니라 표준 값 , 및 `E_UNEXPECTED` `E_FAIL`및 을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="32580-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="32580-111">Return value</span></span>|<span data-ttu-id="32580-112">Description</span><span class="sxs-lookup"><span data-stu-id="32580-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="32580-113">이미지가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32580-113">The image is invalid.</span></span> <span data-ttu-id="32580-114">이 값은 HRESULT 0xC000007BL입니다.</span><span class="sxs-lookup"><span data-stu-id="32580-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="32580-115">이미지가 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-115">The image is valid.</span></span> <span data-ttu-id="32580-116">이 값은 HRESULT 0x00000000L입니다.</span><span class="sxs-lookup"><span data-stu-id="32580-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32580-117">설명</span><span class="sxs-lookup"><span data-stu-id="32580-117">Remarks</span></span>  
 <span data-ttu-id="32580-118">Windows XP 및 이후 버전에서 운영 체제 로더는 COFF(공통 개체 파일 형식) 헤더의 COM 설명자 디렉토리 비트를 검사하여 관리되는 모듈을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="32580-119">설정된 비트는 관리되는 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32580-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="32580-120">로더가 관리되는 모듈을 감지하면 MsCorEE.dll을 `_CorValidateImage`로드하고 다음 작업을 수행하는 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="32580-121">이미지가 유효한 관리 모듈임을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="32580-122">이미지의 진입점을 공통 언어 런타임(CLR)의 진입점으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="32580-123">64비트 버전의 Windows의 경우 메모리에 있는 이미지를 PE32에서 PE32+ 형식으로 변환하여 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="32580-124">관리되는 모듈 이미지가 로드되면 로더로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="32580-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="32580-125">실행 가능한 이미지의 경우 운영 체제 로더는 실행 _CorExeMain 에 지정된 진입점에 관계없이 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="32580-126">DLL 어셈블리 이미지의 경우 로더는 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="32580-127">`_CorExeMain`또는 `_CorDllMain` 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="32580-128">CLR을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="32580-129">어셈블리의 CLR 헤더에서 관리되는 진입점을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="32580-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="32580-130">실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-130">Begins execution.</span></span>  
  
 <span data-ttu-id="32580-131">로더는 관리되는 모듈 이미지가 언로드될 때 [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="32580-132">그러나 이 함수는 어떠한 작업도 수행하지 않습니다. 그냥 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32580-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32580-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32580-133">Requirements</span></span>  
 <span data-ttu-id="32580-134">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32580-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32580-135">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="32580-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32580-136">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="32580-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32580-137">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32580-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32580-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32580-138">See also</span></span>

- [<span data-ttu-id="32580-139">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="32580-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
