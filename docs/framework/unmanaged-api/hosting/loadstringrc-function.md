---
title: LoadStringRC 함수
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176242"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="c64a9-102">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="c64a9-102">LoadStringRC Function</span></span>
<span data-ttu-id="c64a9-103">현재 스레드의 기본 문화권에서 HRESULT 값을 오류 메시지로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="c64a9-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64a9-105">구문</span><span class="sxs-lookup"><span data-stu-id="c64a9-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c64a9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c64a9-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="c64a9-107">【인】 Hresult.</span><span class="sxs-lookup"><span data-stu-id="c64a9-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="c64a9-108">【아웃】 성공적으로 완료되면 오류 메시지가 포함된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="c64a9-109">【인】 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="c64a9-110">【인】 무시.</span><span class="sxs-lookup"><span data-stu-id="c64a9-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c64a9-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="c64a9-111">Return Value</span></span>  
 <span data-ttu-id="c64a9-112">이 메서드는 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="c64a9-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="c64a9-113">Return code</span></span>|<span data-ttu-id="c64a9-114">Description</span><span class="sxs-lookup"><span data-stu-id="c64a9-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c64a9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c64a9-115">S_OK</span></span>|<span data-ttu-id="c64a9-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="c64a9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c64a9-117">E_INVALIDARG</span></span>|<span data-ttu-id="c64a9-118">`szBuffer`null이거나 `iMax` 0(0)입니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c64a9-119">설명</span><span class="sxs-lookup"><span data-stu-id="c64a9-119">Remarks</span></span>  
 <span data-ttu-id="c64a9-120">메서드가 성공적으로 완료되지 `szBuffer` 않으면 빈 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64a9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c64a9-121">Requirements</span></span>  
 <span data-ttu-id="c64a9-122">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c64a9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c64a9-123">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="c64a9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c64a9-124">**라이브러리:** MSCorEE.dll 과 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="c64a9-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="c64a9-125">MScorwks.dll 대신 MSCorEE.dll을 사용하여 .NET 프레임워크의 올바른 버전을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c64a9-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c64a9-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c64a9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64a9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c64a9-127">See also</span></span>

- [<span data-ttu-id="c64a9-128">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="c64a9-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="c64a9-129">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c64a9-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
