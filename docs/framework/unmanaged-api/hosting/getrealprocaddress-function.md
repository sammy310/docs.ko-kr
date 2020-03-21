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
ms.openlocfilehash: 4c914e00987053b1c1e9e00bf8e54632175e1de8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178169"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="06a6f-102">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="06a6f-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="06a6f-103">공통 언어 런타임(CLR)의 최신 설치된 버전에서 내보낸 지정된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="06a6f-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a6f-105">구문</span><span class="sxs-lookup"><span data-stu-id="06a6f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06a6f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06a6f-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="06a6f-107">【인】 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="06a6f-108">【아웃】 함수의 주소에 대한 포인터를 받는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06a6f-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="06a6f-109">Return Value</span></span>  
 <span data-ttu-id="06a6f-110">이 메서드는 CorError.h에 정의된 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="06a6f-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="06a6f-111">Return code</span></span>|<span data-ttu-id="06a6f-112">Description</span><span class="sxs-lookup"><span data-stu-id="06a6f-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="06a6f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="06a6f-113">S_OK</span></span>|<span data-ttu-id="06a6f-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="06a6f-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="06a6f-115">E_POINTER</span></span>|<span data-ttu-id="06a6f-116">`ppv`가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="06a6f-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="06a6f-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="06a6f-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="06a6f-118">함수는 런타임에서 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06a6f-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06a6f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06a6f-119">Requirements</span></span>  
 <span data-ttu-id="06a6f-120">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06a6f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a6f-121">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="06a6f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06a6f-122">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="06a6f-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06a6f-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a6f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a6f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06a6f-124">See also</span></span>

- [<span data-ttu-id="06a6f-125">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="06a6f-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
