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
ms.openlocfilehash: d48106fca6008955409581ad9ac202aebe785cb4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733232"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="d4fcf-102">GetRealProcAddress 함수</span><span class="sxs-lookup"><span data-stu-id="d4fcf-102">GetRealProcAddress Function</span></span>

<span data-ttu-id="d4fcf-103">최신 버전의 CLR (공용 언어 런타임)에서 내보낸 지정 된 함수의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="d4fcf-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fcf-105">구문</span><span class="sxs-lookup"><span data-stu-id="d4fcf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4fcf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4fcf-106">Parameters</span></span>  

 `pwszProcName`  
 <span data-ttu-id="d4fcf-107">진행 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d4fcf-108">제한이 함수 주소에 대 한 포인터를 수신 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4fcf-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4fcf-109">Return Value</span></span>  

 <span data-ttu-id="d4fcf-110">이 메서드는 Winerror.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드와 CorError. h에 정의 된 다음 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="d4fcf-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="d4fcf-111">Return code</span></span>|<span data-ttu-id="d4fcf-112">설명</span><span class="sxs-lookup"><span data-stu-id="d4fcf-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d4fcf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4fcf-113">S_OK</span></span>|<span data-ttu-id="d4fcf-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d4fcf-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d4fcf-115">E_POINTER</span></span>|<span data-ttu-id="d4fcf-116">`ppv`가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="d4fcf-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="d4fcf-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="d4fcf-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="d4fcf-118">함수는 런타임에서 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4fcf-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4fcf-119">Requirements</span></span>  

 <span data-ttu-id="d4fcf-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4fcf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4fcf-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4fcf-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4fcf-122">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4fcf-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4fcf-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4fcf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fcf-124">참조</span><span class="sxs-lookup"><span data-stu-id="d4fcf-124">See also</span></span>

- [<span data-ttu-id="d4fcf-125">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d4fcf-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
