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
ms.openlocfilehash: 66d4c14234c7929af443922f86098b46a4aa6eb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122012"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="7abd9-102">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="7abd9-102">LoadStringRC Function</span></span>
<span data-ttu-id="7abd9-103">현재 스레드의 기본 문화권을 사용 하 여 HRESULT 값을 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="7abd9-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abd9-105">구문</span><span class="sxs-lookup"><span data-stu-id="7abd9-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7abd9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7abd9-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="7abd9-107">진행 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="7abd9-108">제한이 성공적으로 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="7abd9-109">진행 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="7abd9-110">진행 무시.</span><span class="sxs-lookup"><span data-stu-id="7abd9-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abd9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7abd9-111">Return Value</span></span>  
 <span data-ttu-id="7abd9-112">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="7abd9-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="7abd9-113">Return code</span></span>|<span data-ttu-id="7abd9-114">설명</span><span class="sxs-lookup"><span data-stu-id="7abd9-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7abd9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="7abd9-115">S_OK</span></span>|<span data-ttu-id="7abd9-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="7abd9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7abd9-117">E_INVALIDARG</span></span>|<span data-ttu-id="7abd9-118">`szBuffer` null 이거나 `iMax`가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7abd9-119">주의</span><span class="sxs-lookup"><span data-stu-id="7abd9-119">Remarks</span></span>  
 <span data-ttu-id="7abd9-120">메서드가 성공적으로 완료 되지 않으면 `szBuffer`에 빈 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7abd9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7abd9-121">Requirements</span></span>  
 <span data-ttu-id="7abd9-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7abd9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7abd9-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7abd9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7abd9-124">**라이브러리:** Mscoree.dll 및 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="7abd9-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="7abd9-125">Mscorwks.dll 대신 Mscoree.dll을 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7abd9-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7abd9-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7abd9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abd9-127">참조</span><span class="sxs-lookup"><span data-stu-id="7abd9-127">See also</span></span>

- [<span data-ttu-id="7abd9-128">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="7abd9-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="7abd9-129">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="7abd9-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
