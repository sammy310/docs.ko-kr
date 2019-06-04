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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d985ed3b7af2aec7da709c3bbbfd10312e5e3a9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490195"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="d5b5f-102">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="d5b5f-102">LoadStringRC Function</span></span>
<span data-ttu-id="d5b5f-103">HRESULT 값을 현재 스레드의 기본 문화권을 사용 하 여 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="d5b5f-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b5f-105">구문</span><span class="sxs-lookup"><span data-stu-id="d5b5f-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b5f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5b5f-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="d5b5f-107">[in] An HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d5b5f-108">[out] 성공적으로 완료 되는 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="d5b5f-109">[in] 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="d5b5f-110">[in] Ignored.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5b5f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d5b5f-111">Return Value</span></span>  
 <span data-ttu-id="d5b5f-112">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d5b5f-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="d5b5f-113">Return code</span></span>|<span data-ttu-id="d5b5f-114">설명</span><span class="sxs-lookup"><span data-stu-id="d5b5f-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d5b5f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5b5f-115">S_OK</span></span>|<span data-ttu-id="d5b5f-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="d5b5f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d5b5f-117">E_INVALIDARG</span></span>|<span data-ttu-id="d5b5f-118">`szBuffer` 이 null 또는 `iMax` 은 영 (0).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5b5f-119">설명</span><span class="sxs-lookup"><span data-stu-id="d5b5f-119">Remarks</span></span>  
 <span data-ttu-id="d5b5f-120">메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b5f-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5b5f-121">Requirements</span></span>  
 <span data-ttu-id="d5b5f-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b5f-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5b5f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5b5f-124">**라이브러리:** MSCorEE.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d5b5f-125">Mscorwks.dll 대신 MSCorEE.dll을 올바른 버전의.NET Framework 대상 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d5b5f-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b5f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b5f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5b5f-127">See also</span></span>

- [<span data-ttu-id="d5b5f-128">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="d5b5f-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="d5b5f-129">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d5b5f-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
