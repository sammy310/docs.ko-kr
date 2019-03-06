---
title: GetRealProcAddress 함수
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6826ee1b94f9a1c48c19150271ebc84ac54dda25
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471786"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="a7e99-102">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="a7e99-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="a7e99-103">사용 하는 CLR (공용 언어 런타임)의 최신 설치 버전에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="a7e99-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e99-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7e99-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7e99-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7e99-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="a7e99-107">[in] 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="a7e99-108">[out] 함수 주소에 대 한 포인터를 수신 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7e99-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7e99-109">Return Value</span></span>  
 <span data-ttu-id="a7e99-110">이 메서드는 CorError.h에 정의 된 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="a7e99-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="a7e99-111">Return code</span></span>|<span data-ttu-id="a7e99-112">설명</span><span class="sxs-lookup"><span data-stu-id="a7e99-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a7e99-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7e99-113">S_OK</span></span>|<span data-ttu-id="a7e99-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="a7e99-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a7e99-115">E_POINTER</span></span>|<span data-ttu-id="a7e99-116">`ppv`가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="a7e99-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="a7e99-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="a7e99-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="a7e99-118">런타임에서 함수를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e99-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7e99-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7e99-119">Requirements</span></span>  
 <span data-ttu-id="a7e99-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7e99-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e99-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7e99-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7e99-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7e99-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7e99-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e99-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e99-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7e99-124">See also</span></span>
- [<span data-ttu-id="a7e99-125">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="a7e99-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
