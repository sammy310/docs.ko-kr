---
description: '자세히 알아보기: GetRealProcAddress 함수'
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
ms.openlocfilehash: b8b3db77d6aef7fae3045a7aa2310c1fadc70e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785317"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="690a4-103">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="690a4-103">GetRealProcAddress Function</span></span>

<span data-ttu-id="690a4-104">최신 버전의 CLR (공용 언어 런타임)에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-104">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="690a4-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690a4-106">구문</span><span class="sxs-lookup"><span data-stu-id="690a4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="690a4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="690a4-107">Parameters</span></span>  

 `pwszProcName`  
 <span data-ttu-id="690a4-108">진행 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-108">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="690a4-109">제한이 함수 주소에 대 한 포인터를 수신 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-109">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="690a4-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="690a4-110">Return Value</span></span>  

 <span data-ttu-id="690a4-111">이 메서드는 Winerror.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드와 CorError. h에 정의 된 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-111">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="690a4-112">반환 코드</span><span class="sxs-lookup"><span data-stu-id="690a4-112">Return code</span></span>|<span data-ttu-id="690a4-113">설명</span><span class="sxs-lookup"><span data-stu-id="690a4-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="690a4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="690a4-114">S_OK</span></span>|<span data-ttu-id="690a4-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="690a4-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="690a4-116">E_POINTER</span></span>|<span data-ttu-id="690a4-117">`ppv`가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="690a4-117">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="690a4-118">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="690a4-118">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="690a4-119">함수는 런타임에서 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="690a4-119">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="690a4-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="690a4-120">Requirements</span></span>  

 <span data-ttu-id="690a4-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="690a4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="690a4-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="690a4-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="690a4-123">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="690a4-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="690a4-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="690a4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690a4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="690a4-125">See also</span></span>

- [<span data-ttu-id="690a4-126">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="690a4-126">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
